<template>
<div class="text-green-400 text-sm mt-4"><span class="w-1/6 inline-block">Tamamlanmışlar</span><span class="text-white">: {{complated.length}} </span></div>
<div class="text-red-400 text-sm"><span class="w-1/6 inline-block">Tamamlanmamışlar</span><span class="text-white">: {{unComplated.length}} </span></div>
</template>
<script>
import { computed } from "@vue/reactivity"

export default {
    props:{
        todoList:Array
    },
    setup(props) {

        const complated = computed(()=> props.todoList.filter(i => i.completed))
        const unComplated = computed(()=> props.todoList.filter(i => !i.completed))
            return {
        complated,
        unComplated
    }
    },

}
</script>