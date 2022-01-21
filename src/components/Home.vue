<template>
  <div>
    <h1>{{ title }}</h1>
    <the-hero-filter
      @hero-search="onHeroSearch"
      @hero-attrs="onAttrsFilter"
    ></the-hero-filter>
    <HeroesGrid :dotaHeroes="filteredHeroes" />
  </div>
</template>

<script>
import HeroesGrid from "./HeroesGrid.vue";
import TheHeroFilter from "./TheHeroFilter.vue";
export default {
  components: { HeroesGrid, TheHeroFilter },
  data() {
    return {
      inputValue: "",
      dotaHeroes: Array,
      filteredHeroes: Array,
    };
  },
  props: {
    title: String,
  },
  methods: {
    getHeroes() {
      const fetchHeroesStats = fetch("https://api.opendota.com/api/heroStats");
      fetchHeroesStats
        .then((response) => {
          return (this.heroStats = response.json());
        })
        .then((data) => {
          this.dotaHeroes = data;
          this.filteredHeroes = data;
        });
    },
    onHeroSearch(heroName) {
      this.filteredHeroes = this.filteredHeroes.filter((item) => {
        return item.localized_name.toLowerCase().includes(heroName);
      });
    },
    onAttrsFilter(attributes) {
      if (attributes.length === 0) {
        return this.filteredHeroes = this.dotaHeroes
      }
        this.filteredHeroes = this.dotaHeroes.filter((item) => {
          return attributes.includes(item.primary_attr)
        });
    },
  },
  created() {
    this.getHeroes();
  },
};
</script>

<style></style>
