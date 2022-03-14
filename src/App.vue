<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import Input from "./components/Todo.vue";
</script>

<template>
  <h1>My To-do list</h1>
  <Input></Input>
</template>

<style>
body,
html,
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  background-color: aliceblue;
}

h1 {
  margin-top: 2em;
  color: #0a325c;
}
</style>
