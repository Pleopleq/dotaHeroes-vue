<template>
  <div >
    <div v-for="hero in this.dotaHeroes" :key="hero.id"> 
      <HeroCard :heroName="hero.localized_name" :heroAttr="hero.primary_attr" />
    </div>
      
  </div>
</template>

<script>
import HeroCard from './HeroCard.vue'
export default {
  data () {
    return  {
      dotaHeroes: Array
    }
  },
  methods: {
    getHeroes() {
      const fetchHeroes = fetch('https://api.opendota.com/api/heroes')
      fetchHeroes.then(response => {
        return response.json()
      })
      .then(data => {
        this.dotaHeroes = data
    });
    }
  },
  components: {
    HeroCard
  },
  created() {
    this.getHeroes()
  }
}

</script>

<style>

</style>