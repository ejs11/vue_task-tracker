<template>
    <div class="tasks_container">
    <div class="Tasks" :key="task.id" v-for="task in sometasks">
        <Task  :task = "task"/>
        
    </div>
    </div>
</template>

<script>
import Task from './Task.vue'

export default {
    name: 'Tasks',
    props: {
        sometasks: Array,
    },
    components: {
        Task
    }
}

</script>


<style scoped>
.tasks_container {
    margin-top: 100px;
}
.Tasks{
    background-color: aliceblue;
    margin: 5px 0px;
}

</style>