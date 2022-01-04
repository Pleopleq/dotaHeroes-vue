<template>
  <div :class="heroAttrColor">
    <h1>{{ heroName }}</h1>
    <img :src="heroImgLink" alt="">
    <p>{{ heroAttr }} </p>
  </div>
</template>
``
<script>
export default {
    props: {
        heroName: String,
        heroAttr: String,
        heroImg: String,
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