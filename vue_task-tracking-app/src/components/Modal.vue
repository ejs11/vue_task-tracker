<template>
    <div id="modal" style="display:none">
        <form action="">
            <div id="title">
            <label for="">Title:</label>
            <input type="text" name="" id=""></div>

            <div id="date">
            <label for="">Date:</label>
            <input type="datetime-local" name="" placeholder=" 0000" id=""></div>

            <div id="check">
                <input type="checkbox" name="" id=""><span>Set Reminder</span>
            </div>

            <div class="btn">
                <Button label="Save Your Task"/>
            </div>
        </form>
    </div>

   

</template>

<script>
import Button from './Button.vue'

export default {
    name: 'Modal',
    components: {
        Button
    }
}
</script>

<style scoped>
* {
    box-sizing: border-box;
    margin: 10px;
    padding: 3px;
}
form {
    width: 100%;background-color: antiquewhite;
    text-align: center;margin: 0px;border: 2px solid navajowhite;
    
}
form > div {
    display: flex;
}
input, textarea , label{
    display: inline-block;
    font-weight: 700;
    width: 180px;
    max-width: 200px;
    border: 1px solid green;
    padding: 10px;
    border-radius:10px ;
    color: gray;
}
input, label {
    margin-left: -40px;
}
label {
    border: none;
    color: black;
}
#modal {
    width: 100%;;margin: 0px auto;display: block;padding: 0;
    margin-top: 20px;box-shadow: 2px 3px 2px navajowhite;
    
    
}
.btn Button {
    padding: 10px 5px;margin: auto;
    box-shadow: 2px 2px 3px gray;
}
#check {
    display: inline-block;
    margin-left: -25px;
}
span {
    display: inline-block;
    margin-left: -90px;color: tomato;
}
</style>