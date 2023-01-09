<template>
    <header>
        <h3>{{title}}</h3>
        <Button label="Add Task"/>
    </header>
</template>

<script>
import Button from './Button.vue'
import Modal from './Modal.vue'

export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: 'Tasks App',
        },
    },
    components: {
        Button,
        Modal,
    }
}
</script>

<style scoped>
header {
    background-color: antiquewhite;
    display: flex;
    justify-content: space-between;
}

h3 {
    font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
    display: inline-block;
    width: 30%;
    padding: 5px;
    color: green;
}
button {
    
}
</style>