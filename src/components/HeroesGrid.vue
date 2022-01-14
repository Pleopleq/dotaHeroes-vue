<template>
  <div class="home_grid">
    <div v-for="hero in dotaHeroes" :key="hero.id">
      <HeroCard 
      :heroName="hero.localized_name"
      :heroAttr="hero.primary_attr"
      :heroImg="hero.img"
      :heroRoles="hero.roles"
      />
    </div>
  </div>
</template>

<script>
import HeroCard from './HeroCard.vue'
export default {
  props: ['dotaHeroes'],
  components: {
    HeroCard
  }
}

</script>

<style scoped>
  .home_grid {
    display: grid;
    grid-auto-rows: 20rem;
    grid-template-columns: repeat(auto-fill, minmax(17rem, 33fr));
    gap: 2rem;
  }
</style>