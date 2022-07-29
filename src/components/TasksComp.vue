<template>
  <div v-for="task in tasks" :key="task.id">
    <TaskComp @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task="task" />
  </div>
</template>

<script>
import TaskComp from '@/components/TaskComp.vue'

export default {
  name: 'TasksComp',
  props: {
    tasks: Array
  },
  components: {
    TaskComp
  },
  emits: ['delete-task', 'toggle-reminder']
}
</script>

<style scope>

</style>