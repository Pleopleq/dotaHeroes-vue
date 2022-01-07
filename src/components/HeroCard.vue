<template>
  <div class="hero" :class="heroAttrColor" @click="handleHeroModal">
    <h1>{{ heroName }}</h1>
    <img :src="heroImgLink" alt="">
    <p>Primary Attribute</p> <img style="width: 32px" :src="attributeIcon" :alt="heroAttrColor">
  </div>
  <div v-if="isModalClosed" >
    <Modal 
    :isModalClosed="isModalClosed" 
    :handleModalClose="handleHeroModal"
    :title="heroName"
    :body="heroData"
    />
</div>
</template>

<script>
const agiIcon = require('../assets/img/Agility.png')
const strIcon = require('../assets/img/Strength.png')
const intIcon = require('../assets/img/Intelligence.png')
import Modal from './Modal.vue'

export default {
    components: {
        Modal
    },
    props: {
        heroName: String,
        heroAttr: String,
        heroImg: String,
        heroRoles: Array
    },
    data() {
        return  {
            isModalClosed: false,
            heroData: {
                heroAttr: this.heroAttr,
                heroImg: `https://api.opendota.com${this.heroImg}`,
                heroRoles: this.heroRoles
            },
            agiIcon,
            strIcon,
            intIcon
        }
    },
    computed: {
        heroImgLink() {
            return `https://api.opendota.com${this.heroImg}`
        },
        heroAttrColor() {
            if(this.heroAttr === 'str') {
                return 'strength'
            }
            if (this.heroAttr === 'agi') {
                return 'agility'
            }
            return 'intelligence'
        },
        attributeIcon() {
            if(this.heroAttr === 'str') {
                return strIcon
            }
            if (this.heroAttr === 'agi') {
                return agiIcon
            }
            return intIcon
        }
    },
    methods: {
        handleHeroModal() {
            this.isModalClosed = !this.isModalClosed
        }
    }
}
</script>

<style scope>
img {
    width: 100%;
    max-width: 320px;
    height: auto;
}
.hero:hover {
    transform: scale(1.2);
    opacity: 0.9;
}

.strength {
    background-color: #FF3333;
}

.agility {
    background-color: #66FF66;
}

.intelligence {
    background-color: #3399FF;
}

</style>