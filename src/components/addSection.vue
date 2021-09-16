<template>
  <h3 class="text-center text-2xl">Todo List</h3>
    <section>
      <input @keydown.enter="newItem" type="text" class="w-full p-2 rounded-md mt-2 bg-black text-white border border-gray-400 focus:border-white outline-none" placeholder="Yeni Todo">
    </section>
</template>

<script>
export default {
    props:{
        addTodo:Function,
    },
    setup(props) {
        const newItem = (event) => {
            props.addTodo(event.target.value)
            event.target.value=""
        }
        return{newItem}

    }
}
</script>