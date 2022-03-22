<script>
export default {
  name: "ToDoForm",
  props: {
    task: String,
  },
  data() {
    return {};
  },
};
</script>

<template>
  <div class="container">
    <h2 class="mb-5">My ToDo App</h2>
    <form @submit.prevent="$emit('functionTask', task)">
      <div class="d-flex gap-2">
        <input
          v-model="task"
          type="text"
          placeholder="Enter Value"
          class="form-control"
        />
        <button class="btn btn-warning rounded-1">Submit</button>
      </div>
    </form>
  </div>
</template>

<style></style>
