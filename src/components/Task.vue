<template>
    <div>
        <li class="task">{{index}}. {{taskText}}
            <i class="fas fa-times" @click="removeTask(index)"></i>
        </li>     
    </div>
</template>

<script>
    export default{
        name: "Task",
        props:{
            taskText:{
                type: String
            },
            index:{
                type: Number

            }
        },
        methods:{
            removeTask(index){
               this.$emit("remove-task", index)
            }
        }
    }

</script>

<style>

.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  list-style-type: none;
  text-align: start;
  display: flex;
  justify-content: space-between;
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



</style>