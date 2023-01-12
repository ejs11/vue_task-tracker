<template>
  <div class="container">
    <Header @toggle-add-task="toggleAddTask" :showAddTask="showAddTask" />
    <div v-if="showAddTask">
      <Modal @add-task="addTask"  />
    </div>
    
    <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :sometasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Modal from './components/Modal.vue'
import Tasks from './components/Tasks.vue'

export default {
  name: 'App',
  components: {
    Header,
    Modal,
    Tasks,
  },

  data() {
    return {
      tasks:[],
      showAddTask: false
    }
  },

  methods: {

   async   deleteTask(id) {
        if(confirm('Are you sure?')) {
          const res = await fetch(`api/tasks/${id}`, {
            method: 'DELETE',
          })
          res.status === 200 ? (this.tasks = this.tasks.filter((data) => data.id !== id)) :
          alert('error occurred, try again')

          }
        }
      ,


      async toggleReminder(id) {
        const res =  await fetch(`api/tasks/${id}`, {
          method: 'PUT'
        })
        this.tasks = this.tasks.map((task) => task.id == id ? {...task, reminder: !task.reminder} : task)
      },


      async addTask(newTask) {
      const res = await fetch('api/tasks', {
        method: 'POST',
        headers: {
          'content-type': 'application/json'          
        },
        body: JSON.stringify(newTask),
      })
      const data = await res.json()
        this.tasks =[...this.tasks, data]
      },


      toggleAddTask() {
        this.showAddTask = !this.showAddTask
      },


      async fetchTasks() {
        const res = await fetch('api/tasks')
        const data = await res.json()
        return data
      },


      async fetchTask(id) {
        const res = await fetch(`api/tasks/${id}`)
        const data = await res.json()
        return data
      }
  },
  async created() {
    this.tasks = await this.fetchTasks()
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  width: 450px;
  height: auto;
  margin: auto;
  padding: 20px 10px;
  outline: none;
  border: none;
  box-sizing: border-box;
  box-shadow: 3px 2px 3px 2px gray;
}
Button {
  
    border: none;
    outline: none;
    color: white;
    font-weight: 600;
    text-shadow: 0.1em 0.1em 0.3em black;
    box-sizing: border-box;
    background-color: green;

}
</style>
