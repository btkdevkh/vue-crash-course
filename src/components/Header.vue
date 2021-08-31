<template>
  <header>
    <h1>{{ title }}</h1>
    <Button 
      v-show="homePage"
      @btn-click="$emit('btn-click')" 
      :text="showAddTaskForm ? 'Close' : 'Add Task'" 
      :color="showAddTaskForm ? 'red' : 'yellow'" 
    />
  </header>
</template>

<script>
  import Button from './Button.vue';

  export default {
    name: "Header",
    props: {
      title: String,
      showAddTaskForm: Boolean
    },
    components: {
      Button,
    },
    computed: {
      homePage() {
        if(this.$route.path === '/') {
          return true;
        } else {
          return false;
        }
      }
    }
  }
</script>

<style scoped>
  header {
    padding: 25px;
    color: #fff;
    background-color: teal;
  }
</style>