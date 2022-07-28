<template>
  <div class="container">
    <HeaderComp title="something" showAddTask="false" />
    <TasksComp :tasks="tasks"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComp from '@/components/HeaderComp.vue'
import TasksComp from '@/components/TasksComp.vue'


export default {
  name: 'HomeView',
  components: {
    HeaderComp,
    TasksComp
  },
  data () {
    return {
      tasks: []
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'March 1st at 2:30pm',
        reminder: true,
      },
      {
        id: 2,
        text: 'Doctor Appointment',
        day: 'March 2nd at 2:30pm',
        reminder: true,
      },
      {
        id: 3,
        text: 'Pharmacy Appointment',
        day: 'March 23rd at 2:30pm',
        reminder: true,
      },
    ]
  }

}
</script>
