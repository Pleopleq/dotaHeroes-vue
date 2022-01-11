<template>
    <div>
      <label for="name">{{label}}</label>
      <input 
        type="text"
        :value="modelValue"
        :placeholder="placeholder"
        @input="(e) => $emit('update:modelValue', e.target.value)"
      >
    </div>
</template>

<script>
export default {
    props: {
        label: String,
        placeholder: String,
        modelValue: String
    }
}
</script>

<style>

</style>