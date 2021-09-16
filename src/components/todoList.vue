<template>
    <section class="mt-4">

<TodoListItem  @delete-event="$emit('delete-event',$event)" v-for="todoItem in todoList" :key="todoItem.id" :todo="todoItem"  />
<Summary :todoList="todoList" />
<small>{{todoLenght}} adet Todo vardır...</small>
    </section>

</template>

<script>
import Summary from "./Summary.vue"
import TodoListItem from "./todoListItem.vue"
import {computed} from 'vue'
export default {
        components:{
        Summary,
        TodoListItem
    },
    props:{
        todoList:Array,
    },
    setup(props){
        const todoLenght = computed(()=> props.todoList.length)
        return {todoLenght}
    }

    
}
</script>