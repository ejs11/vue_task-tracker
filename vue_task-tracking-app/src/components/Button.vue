<template>
    <button>{{label}}</button>
</template>

<script>

export default {
    name: 'Button',
    props: ['label']
}
</script>

<style scoped>
button {
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