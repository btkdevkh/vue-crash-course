<template>
  <div class="about">
    <p>App version 1.0</p>
    <router-link to="/">Go back</router-link>
  </div>
</template>

<script>
export default {
  name: 'About',
}
</script>

<style scoped>
  .about {
    padding: 25px;
    color: white;
    text-align: center;
    background: teal;
  }
  .about a {
    color: black;
  }
</style>