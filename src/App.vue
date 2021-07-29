<template>
  <div id="app">
    <h1> To-do List</h1>
    <div>
      <AddTask @add-task="addTask"/>
      <ul>
        <Task v-for="(task, index) in tasks" :key="index" :index="index" :taskText="task" @remove-task="removeTask" />
      </ul>
    </div>
  </div>
</template>

<script>
import AddTask from './components/AddTask.vue' 
import Task from './components/Task.vue'

export default {
  
  name: "App",
  data: () => ({
    tasks: ["Ir al super", "Hacer la tarea"]

  }),
  methods:{

    removeTask(index){  
      this.tasks.splice(index, 1);
      
    },
    addTask(task){
      this.tasks.push(task)
    }
  },

  components:{
    AddTask,
    Task
  },
}
</script>

<style lang="scss">


#app {
  font-family: Helvetica, sans-serif;
  text-align: center;
  margin-top: 60px;
  display: flex;
  flex-direction: column;
  align-items: center;

}

ul{
  padding: 0;
}
</style>
