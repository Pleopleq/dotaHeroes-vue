<template>
  <div>
      <h1>
          {{ heroName }}
      </h1>
      <p>{{ heroAttr }} </p>
  </div>
</template>

<script>
export default {
    props: {
        heroName: String,
        heroAttr: String
    }
}
</script>

<style>

</style>