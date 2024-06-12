<template>
  <div class="container">
   <Header title="Task Tracker"/>
   <Tasks @delete-task="deleteTask" :tasks="tasks" />
  </div>
</template>

<script>
import Header from './components/header.vue'
import Tasks from './components/tasks.vue'
export default {
  name: "App",
  components: {
    Header,
    Tasks
  },
  data () {
    return {
       tasks: []
    }
  },
  methods: {
deleteTask(id) {
 this.tasks = this.tasks.filter((task) => task.id !== id)
}
  },
  created () {
    this.tasks = [
      {
        id: 1,
        text: "Doctor's Appointment",
        day: "March 1st at 2:30pm",
        reminder: true
      },
        {
        id: 2,
        text: "Doctor's Appointment",
        day: "March 1st at 4:30pm",
        reminder: true
      },
        {
        id: 3,
        text: "Doctor's Appointment",
        day: "March 1st at 2:30pm",
        reminder: true
      },
        {
        id: 4,
        text: "Doctor's Appointment",
        day: "March 1st at 2:30pm",
        reminder: true
      },
        {
        id: 5,
        text: "Lawyer's Appointment",
        day: "March 1st at 8:30pm",
        reminder: false
      }
    ]
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
  background-color: white;
}

.container {
  min-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
</style>
