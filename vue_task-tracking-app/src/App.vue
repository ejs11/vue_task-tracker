<template>
  <div class="container">
    <Header/>
    <Modal/>
    <Tasks :sometasks="tasks"/>
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
      tasks:[]
    }
  },
  created() {
    this.tasks = [
      {
        id:1,
        text: 'Go to the beach',
        date: 'March 1st at 2:30pm',
        reminder: false,
      },
      {
        id:1,
        text: 'Go to the Pitch',
        date: 'March 1st at 2:30pm',
        reminder: true,
      },
      {
        id:1,
        text: 'Get Jogging Time',
        date: 'March 1st at 2:30pm',
        reminder: false,
      },
      {
        id:1,
        text: 'Go to the party',
        date: 'March 1st at 2:30pm',
        reminder: true,
        icon: './assets/logo.png'
      },

    ]
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
