<template>
    <div>
      <label for="name">{{label}}</label>
      <input 
        v-model="modelValue"
        :type="type"
        :placeholder="placeholder"
        @input="emitValue"
      >
    </div>
</template>

<script>
export default {
    data() {
      return {
        modelValue: '',
      }
    },
    props: {
        label: String,
        placeholder: String,
        type: String,
    },
    methods: {
      emitValue() {
        this.$emit('custom-input-event', this.modelValue)
      }
    }
}
</script>

<style>

</style>