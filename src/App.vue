<template>
  <div id="app">
    <Todolist />
  </div>
</template>

<script>
import Todolist from "./components/Todolist.vue";

export default {
  name: "app",
  components: {
    Todolist
  }
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
}

input,
button {
  border: 0;
}
</style>
