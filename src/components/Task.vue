<template>
  <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{ task.text }}</h3>
    <small>Date: {{ task.date }}</small>
    <i @click="handleDelete(task.id)" class="fas fa-trash"></i>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  },
  methods: {
    handleDelete(id) {
      this.$emit('delete-task', id)
    }
  },
}
</script>

<style scoped>
  .task {
    position: relative;
    padding: 15px;
    margin: 0 0 2px 0;
    color: white;
    background: rgba(0,0,0,0.5);
  }
  .reminder {
    border-left: 8px solid orange;
  }
  .fa-trash {
    position: absolute;
    top: 50%;
    right: 20px;
    color: #d83b3b;
    cursor: pointer;
    transform: translateY(-50%);
  }
</style>
