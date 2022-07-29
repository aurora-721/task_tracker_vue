<template>
  <header>
    <h1>{{ title }}</h1>
    <Button 
      @btn-click="$emit('toggle-add-task')" 
      :text="showAddTask ? 'Close' : 'Add Task'" 
      :color="showAddTask ? 'red' : 'green'" 
      color="green"/>
  </header>
</template>

<script>
import Button from './ButtonComp.vue'
export default {
  name: 'Header',
  props: {
    title: String,
    showAddTask: Boolean
  },
  components: {
    Button,
  },
  emits: ['toggle-add-task']
}
</script>

<style scope>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>