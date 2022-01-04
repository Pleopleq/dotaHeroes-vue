<template>
  <div>
      <h1>{{ title }} </h1>
      <HeroesGrid/>
  </div>
</template>

<script>
import HeroesGrid from './HeroesGrid.vue'
export default {
  components: { HeroesGrid },
  props: {
      title: String
  }

}
</script>

<style>

</style>