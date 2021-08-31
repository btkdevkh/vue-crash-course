<template>
  <button 
    @click="onClick()"
    :style="{background: color}"
  > {{ text }}
  </button>
</template>

<script>
  export default {
    name: "Button",
    props: {
      text: String,
      color: String
    },
    methods: {
      onClick() {
        this.$emit('btn-click');
      }
    },
  }
</script>

<style scoped>
  button {
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    text-transform: uppercase;
  }
</style>