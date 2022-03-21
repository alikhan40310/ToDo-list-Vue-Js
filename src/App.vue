<script>
import ToDoList from "./components/toDoList.vue";
import TheWelcome from "./components/TheWelcome.vue";
import Watchers from "./components/Watchers.vue";
import ToDoForm from "./components/ToDoForm.vue";

export default {
  name: "App",
  components: {
    ToDoList,
    ToDoForm,
    Watchers,
    TheWelcome,
  },
  data() {
    return {
      value: "",
      deleteTable: "",
      task: "",
      todos: [ ],
    };
  },
  methods: {
    TaskSubmit(task) {
      console.log("TaskSubmit", task);
    },
  },
};
</script>

<template>
  <ToDoForm class="cusStyle" @function-task="TaskSubmit" />

  <ToDoList :todos="todos" />
  <!-- <TheWelcome></TheWelcome>  -->
  <!-- <Watchers></Watchers> -->
</template>

<style>
@import "./assets/base.css";
.cusStyle {
  margin-top: 5rem;
}
</style>
