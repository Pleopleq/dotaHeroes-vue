<template>
  <div>
      <h1>{{ title }}</h1>
      <CustomInput
      v-model="heroName"
      :placeholder="'Hero name to search...'"
      :label="'Hero Search:'"
      />
      <button>Search</button>
      <HeroesGrid :dotaHeroes="dotaHeroes"/>
  </div>
</template>

<script>
import HeroesGrid from './HeroesGrid.vue'
import CustomInput from './CustomInput.vue'
export default {
  components: { HeroesGrid, CustomInput },
  data() {
      return {
          heroName: '',
          dotaHeroes: Array,
      }
  },
  props: {
      title: String
  },
    methods: {
    getHeroes() {
      const fetchHeroesStats = fetch('https://api.opendota.com/api/heroStats')
      fetchHeroesStats.then(response => {
        return this.heroStats = response.json()
      })
      .then(data => {
        this.dotaHeroes = data
      });
    }
  },
  created() {
    this.getHeroes()
  }
}
</script>

<style>

</style>