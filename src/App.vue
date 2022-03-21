<script>
import ToDoList from "./components/toDoList.vue";
import TheWelcome from "./components/TheWelcome.vue";
import Watchers from "./components/Watchers.vue";
import ToDoForm from "./components/ToDoForm.vue";

// save data in local storage
let storeDatas = JSON.parse(localStorage.getItem("toDoList"));
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
      todos: storeDatas ? storeDatas : [],
      editedTask: null,
    };
  },
  methods: {
    TaskSubmit(task) {
      if (task.length === 0) {
        return;
      }
      if (this.editedTask === null) {
        this.todos.push({
          name: task,
          status: "to-do",
        });
      } else {
        this.todos[this.editedTask].name = task;
        this.editedTask = null;
      }

      localStorage.setItem("toDoList", JSON.stringify(this.todos));
    },
    DeleteTask(index) {
      if (confirm("Are you sure?")) {
        this.todos.splice(index, 1);
        // delete item from local storage
        localStorage.setItem("toDoList", JSON.stringify(this.todos));
      }
      console.log(index);
    },
    editTask(index) {
      this.task = this.todos[index].name;
      this.editedTask = index;
      console.log(index);
    },
  },
};
</script>

<template>
  <ToDoForm :task="task" class="cusStyle" @function-task="TaskSubmit" />
  <ToDoList
    :todos="todos"
    @delete-params="DeleteTask"
    @edit-params="editTask"
  />
  <!-- <TheWelcome></TheWelcome>  -->
  <!-- <Watchers></Watchers> -->
</template>

<style>
@import "./assets/base.css";
.cusStyle {
  margin-top: 5rem;
}
</style>
