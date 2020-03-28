<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo5.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{ todo5.title }}</p>
            <!-- send todo.id as payload of button click -->
            <!-- we have to send the id up levels to Todos and App to get to where data is so we use emit -->
            <!-- del-todo is name and then parameter -->
            <button @click="$emit('del-todo', todo5.id)" class="del">x</button>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo5"],
    methods: {
        markComplete() {
            console.log(123)
            this.todo5.completed = !this.todo5.completed;
        }
    }
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9x;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>