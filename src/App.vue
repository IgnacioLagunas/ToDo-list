<template>
  <div id="app">
    <h1> To-do List</h1>
    <div>
      <AddTask @add-task="addTask"/>
      <ul>
        <li class="task" v-for="(task, index) in tasks" :key="index">
          {{index}}. {{task}}
          <i @click="removeTask(index)" class="fas fa-times"></i>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import AddTask from './components/AddTask.vue' 

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

.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  list-style-type: none;
  text-align: start;
  display: flex;
  justify-content: space-between;
}

i{
   cursor: pointer;
}

i:hover{
  color: red;
}

ul{
  padding: 0;
}
</style>
