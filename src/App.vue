<template>
<div class="bg-gray-600 rounded-md shadow-md  w-[800px]   text-white mx-auto p-3">
<AddSection />
<TodoList />
</div>
</template>
<script>
import TodoList from "./components/todoList.vue"
import AddSection from "./components/addSection.vue"
import {ref,reactive} from'vue'
export default{
  components:{TodoList,AddSection},
  setup(){
    const todoList=ref([

    ])
    return{todoList}
  }
}
</script>