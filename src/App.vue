<template>
  <div class="container">
    <Header 
      title="Task Tracker" 
      @btn-click="toggleAddTask" 
      :showAddTaskForm="showAddTaskForm" 
    />
    <router-view :showAddTaskForm="showAddTaskForm"></router-view>
    <Footer />
  </div>
</template>

<script>
  import Header from './components/Header';
  import Footer from './components/Footer.vue';

  export default {
    name: 'App',
    components: {
      Header,
      Footer
    },
    data() {
      return {
        showAddTaskForm: false
      }
    },
    methods: {
      toggleAddTask() {
        this.showAddTaskForm = !this.showAddTaskForm;
      }
    },
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>
