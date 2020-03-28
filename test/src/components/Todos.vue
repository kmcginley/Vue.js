<template>
    <div>
        <h3>Todos </h3>
        <div v-bind:key="todo.id" v-for="todo in todos3">
            <!-- have to send id up one more level to App -->
            <!-- catch del-todo name defined from TodoItem -->
            <TodoItem v-bind:todo5="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';


export default {
    name: "export1",
    components: {
        TodoItem
    },
    props: ["todos3"]
}
</script>

<style scoped>

</style>