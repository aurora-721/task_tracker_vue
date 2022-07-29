<template>
  <div class="container">
    <HeaderComp @toggle-add-task="toggleAddTask" 
      title="Task tracker"
      :showAddTask="showAddTask" />
    <div v-show="showAddTask">
      <AddTask @add-task="addTask" />
    </div>
    <TasksComp @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HeaderComp from '@/components/HeaderComp.vue'
import TasksComp from '@/components/TasksComp.vue'
import AddTask from '@/components/AddTask.vue'


export default {
  name: 'HomeView',
  components: {
    HeaderComp,
    TasksComp,
    AddTask
  },
  data () {
    return {
      tasks: [],
      showAddTask: false
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id) {
      if(confirm('Are you sure?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)

      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id
      ? {...task, reminder: !task.reminder }
      : task)
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
        reminder: false,
      },
    ]
  }

}
</script>
