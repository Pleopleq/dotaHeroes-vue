<template>
  <div>
      <h1>{{ title }}</h1>
      <CustomInput
      v-model="heroName"
      :placeholder="'Hero name to search...'"
      :label="'Hero Search:'"
      />
      <button>Search</button>
      <HeroesGrid/>
  </div>
</template>

<script>
import HeroesGrid from './HeroesGrid.vue'
import CustomInput from './CustomInput.vue'
export default {
  components: { HeroesGrid, CustomInput },
  data() {
      return {
          heroName: ''
      }
  },
  props: {
      title: String
  }
}
</script>

<style>

</style>