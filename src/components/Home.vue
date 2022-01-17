<template>
  <div>
      <h1>{{ title }}</h1>
      <CustomInput
      v-model="heroName"
      :placeholder="'Hero name to search...'"
      :label="'Hero Search:'"
      @keypress="onChangeFilter"
      />
      <HeroesGrid 
      :dotaHeroes="filteredHeroes"
      />
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
          filteredHeroes: Array
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
        this.filteredHeroes = data
      });
    },
    onChangeFilter() {
      this.filteredHeroes = this.dotaHeroes.filter(item => {
         return item.localized_name.toLowerCase().includes(this.heroName) 
      })
    }
  },
  created() {
    this.getHeroes()
  }
}
</script>

<style>

</style>