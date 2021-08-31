<template>
  <footer>
    <p>Copyright &copy; Task Tracker {{new Date().getFullYear()}}</p>
    <router-link to="/about">About</router-link>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>
  footer {
    text-align: center;
    padding: 25px;
  }
  footer a {
    color: teal;
  }
</style>
