<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import store from "./store";
import TaskList from "./components/TaskList.vue";

export default {
  name: "app",
  store,
  components: {
    TaskList
  }
};
</script>

<style>
@import "./index.css";
</style>
