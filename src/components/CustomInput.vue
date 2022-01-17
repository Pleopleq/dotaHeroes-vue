<template>
    <div>
      <label for="name">{{label}}</label>
      <input 
        type="text"
        :value="modelValue"
        :placeholder="placeholder"
        @change="onChange"
        @input="(e) => $emit('update:modelValue', e.target.value)"
      >
    </div>
</template>

<script>
export default {
    props: {
        label: String,
        placeholder: String,
        modelValue: String,
        onChange: Function
    }
}
</script>

<style>

</style>