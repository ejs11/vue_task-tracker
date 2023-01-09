<template>
    <button @click="onClickeed()">{{label}}</button>
</template>

<script>

export default {
    name: 'Button',
    props: ['label'],

    methods: {
    onClickeed() {
        document.getElementById()
    },
},


}
</script>

<style scoped>
button {
    width: 100px;
    height: 48px;
    margin: 10px;
    border-radius: 10px;
    border: none;
    outline: none;
    color: white;
    font-weight: 600;
    text-shadow: 0.1em 0.1em 0.3em black;
    box-sizing: border-box;
    background-color: green;
}
button:hover {
    background-color: rgba(0, 128, 0, 0.726);
    transition: all 0.3s;
}
</style>