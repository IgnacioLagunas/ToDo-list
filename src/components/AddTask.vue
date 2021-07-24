<template>
    <div>
        <h2>Tarea</h2>
        <input v-model="newTask" type="text" placeholder="Escriba aqui su tarea">
        <button @click="addTask">Agregar</button>
    </div>
</template>

<script>
    export default{
        name: 'AddTask',
        
        data(){
            return {
                newTask: ""
            }
        },
        methods:{
            addTask(){
                this.$emit('add-task', this.newTask);
                this.newTask = "";
            }
        }
    }
    
</script>

<style scoped>
    div{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    h2{
        font-size: 2rem;
    }
    input{
        margin: 0 1rem;
        border: solid black 1px;
        padding: 10px 20px;
        border-radius: 5px;
        cursor: pointer;
        text-decoration: none;
        font-size: 15px;
        font-family: inherit;
    }
    button {
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