<script setup>
import { ref } from "vue";

const input = ref("");
const todos = ref([]);

function addTodo() {
  todos.value.push({ text: input.value, done: false });
  input.value = "";
}

function removeTodo(todo) {
  console.log(todo, todos.value )
  todos.value = todos.value.filter((todoObj) => todoObj !== todo);
}

function toggleDone(todo) {
  todo.done = !todo.done;
}
</script>

<template>
  <main class="container">
    <div>
      <input
        class="input-field"
        v-model="input"
        placeholder="Write a to-do..."
      />
      <button @click="addTodo">Add Todo</button>
    </div>
    <ul class="list">
      <li class="list-item" v-for="todo in todos" :key='todo.text'>
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
        <div>
          <button @click="removeTodo(todo)">Remove</button>
          <button @click="toggleDone(todo)">Done</button>
        </div>
      </li>
    </ul>
  </main>
</template>

<style>
span {
  padding: 1em 3em;
  font-size: 1.4rem;
  font-weight: bold;
}

input {
  margin: 0.5em;
  padding: 0.5em;
}


button {
  margin: 1em;
  padding: 0.5em;
  background-color: rgba(127, 168, 255, 0.363);
  box-shadow: 10px 5px 5px rgba(0, 0, 0, 0.541);
  border-radius: 8px;
}

.done {
  text-decoration: line-through;
}

.list {
  padding-left: 0;
}

.list-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  list-style: none;
  margin-top: 1em;
  border: 1px dotted grey;
  padding: 0.5em;
  background-color: rgba(128, 128, 128, 0.116);
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
