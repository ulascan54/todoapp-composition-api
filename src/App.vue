<template>
<div class="bg-gray-600 rounded-md shadow-md  w-[800px]   text-white mx-auto p-3">
<AddSection :addTodo="addTodo" />
<TodoList @delete-event="deleteItem" :todoList="todoList" />
</div>
</template>
<script>
import TodoList from "./components/todoList.vue"
import AddSection from "./components/addSection.vue"
import {ref} from'vue'
export default{
  components:{TodoList,AddSection},
  setup(){
    const todoList=ref([
    ])
    const addTodo= (todoText) => {
      todoList.value.push({
        id: new Date().getTime(),
        title: todoText,
        completed:false,
      })
    }
    const deleteItem=(id)=>{
      todoList.value=todoList.value.filter(f=> f.id !==id)
    }
    return{todoList , addTodo ,deleteItem}
  }
}
</script>