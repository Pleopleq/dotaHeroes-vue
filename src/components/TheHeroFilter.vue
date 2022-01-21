<template>
  <div>
    <form @submit.prevent="submitHeroSearch">
      <div>
        <label for="name">Hero Name: </label>
        <input type="text" v-model="heroName" />
        <button type="submit">Search</button>
      </div>
    </form>
    <form @submit.prevent="submitHeroAttrs">
      <div class="attr_filters">
        <div>
          <label for="strHeroes">Strength Heroes</label>
          <input
            id="attributes"
            name="attributes"
            type="checkbox"
            value="str"
            v-model="attributes"
          />
        </div>
        <div>
          <label for="agiHeroes">Agility Heroes</label>
          <input
            id="attributes"
            name="attributes"
            type="checkbox"
            value="agi"
            v-model="attributes"
          />
        </div>
        <div>
          <label for="intHeroes">Inteligence Heroes</label>
          <input
            id="attributes"
            name="attributes"
            type="checkbox"
            value="int"
            v-model="attributes"
          />
        </div>
      </div>
      <div>
        <button>Filter</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      heroName: "",
      attributes: [],
    };
  },
  methods: {
    submitHeroSearch() {
      this.$emit("hero-search", this.heroName);
    },
    submitHeroAttrs() {
      this.$emit("hero-attrs", this.attributes);
    },
  },
};
</script>

<style scoped>
.attr_filters {
  display: flex;
  justify-content: space-evenly;
  padding: 1rem 1rem 0 1rem;
}
</style>
