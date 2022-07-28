<template>
  <div v-for="task in tasks" :key="task.id">
    <TaskComp :task="task" />
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
  }
}
</script>

<style scope>

</style>