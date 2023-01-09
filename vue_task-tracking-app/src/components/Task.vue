<template>
    <div :class="[task.reminder ? 'true' : 'false',]" class="Task">
        <div> <i :class="[task.reminder ? 'visible' : 'hidden',]" class="material-icons visible" id="visible">schedule</i> {{ task.text }}</div>
        <div>{{ task.date }} <i class="material-icons">delete</i></div>
    </div>
</template>


<script>

export default {
    name: 'Task',
    props: {
        task: Object,
    }
}

</script>

<style scoped>
#visible {
    color: green;
}
.visible {
    visibility: visible;
}
.hidden {
    color: green;
    visibility: hidden;;
}
.Task > div {
    width: 250px;
    cursor: pointer;
    padding: 20px 0px;
}
.Task > div:first-child {
    text-align: left;
    font-weight: bold;
    font-family: "Trirong", serif;
    padding-left: 25px;
}
.Task > div:last-child {
    text-decoration: underline;
    font-size: small;
    font-style: oblique;
}
.Task {
    
    display: flex;
    justify-content: space-between;
}
.true {
    border-left: 2px solid green;
}
.false {
    border-left: 2px solid hwb(0 82% 15%);
}
.material-icons {
    font-size: 18px;
    margin-right: 25px;
    cursor: pointer;
    color: tomato;
    float: right;
    border-radius: 50%;
}
.material-icons:hover {
    color: red;
}
</style>