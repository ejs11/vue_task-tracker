<template>
    <div class="tasks_container">
    <div class="Tasks" :key="task.id" v-for="task in sometasks">
        <Task @toggle-reminder="$emit('toggle-reminder', task.id)"  @delete-task="$emit('delete-task', task.id)" :task = "task"/>
        
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
    },
    emits: ['delete-task','toggle-reminder']
}

</script>


<style scoped>
.tasks_container {
    display: flex;
    flex-direction: column-reverse;
    margin-top: 10px;
}
.Tasks{
    background-color: aliceblue;
    margin: 5px 0px;
    transition: all 5s;
}
</style>