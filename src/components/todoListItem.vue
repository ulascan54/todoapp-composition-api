<template>
              <div class="bg-400 flex justify-between items-center even:bg-gray-400 bg-gray-500 bg-opacity-50 even:bg-opacity-50 hover:bg-opacity-100 rounded-md  px-2 py-1 mt-2">
                <label :for="`todo_${todo.id}_completed`" >
                  <input v-model="todo.completed" type="checkbox" :id="`todo_${todo.id}_completed`" @click="todo.completed=!todo.completed">
                  <span class="text-lg ml-3">{{todo.title}}</span>
                </label>
                <button class="bg-red-700 py-1 px-4 rounded-md opacity-70 hover:opacity-100 transition-opacity" @click="deleteTodo(todo.id)">Sil</button>
              </div>
</template>
<script>
import {computed} from 'vue'
export default {
    props:{
        todo:Object,
    },
    setup(props,{emit}){
      const deleteTodo =(id)=>{
        emit('delete-event',id)
      }
      return{ deleteTodo}
    }
}
</script>