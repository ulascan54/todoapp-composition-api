<template>
    <section class="mt-4">

<TodoListItem />
<Summary />
    </section>

</template>

<script>
import Summary from "./Summary.vue"
import TodoListItem from "./todoListItem.vue"

export default {
    components:{
        Summary,
        TodoListItem
    }
    
}
</script>