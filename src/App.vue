<template>
  <div>
    <todo-list />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";

export default {
  name: "App",
  components: {
    TodoList
  }
}
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  height: 100%;
}
h1 {
  margin: 0;
  padding: 0;
  color: #070707;
}

</style>
