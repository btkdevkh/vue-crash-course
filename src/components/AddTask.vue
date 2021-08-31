<template>
  <form @submit="onSubmit">
    <input v-model="text" name="text" type="text" placeholder="Add Task ..."><br />
    <input v-model="day" name="day" type="text" placeholder="Add Day & Time"><br />
    <label>Set Reminder </label>
    <input v-model="reminder" name="reminder" type="checkbox"><br />
    <p class="error"><small>{{ error }}</small></p>
    <input type="submit" value="Save Task">
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      text: '',
      day: '',
      reminder: false,
      error: '',
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if(!this.text) {
        this.error = 'Field required';
        return;
      }

      const newTask = {
        //id: Math.floor(Math.random() * 100000),
        text: this.text,
        date: this.day,
        reminder: this.reminder
      }

      this.$emit('add-task', newTask);

      this.text = '';
      this.day = '';
      this.reminder = false;
    }
  },
}
</script>

<style scoped>
  form {
    text-align: left;
    padding: 25px;
    background: slategray;
  }
  form input {
    width: 100%;
    padding: 10px;
    border: none;
    margin: 1px 0;
    border-radius: 5px;
  }
  form input:focus {
    outline: 0;
  }
  label {
    padding: 5px 0;
    color: white;
    display: inline-block
  }
  form input[type="checkbox"] {
    width: 20px;
    vertical-align: middle;
  }
  form input[type="submit"] {
    display: block;
    color: white;
    background: black;
    width: 90px;
    margin: 0 auto;
    cursor: pointer;
  }
  .error {
    color: red;
  }
</style>