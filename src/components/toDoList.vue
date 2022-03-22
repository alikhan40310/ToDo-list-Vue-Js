<script>
export default {
  name: "ToDoList",
  props: {
    task: String,
    todos: Array,
  },
  data() {
    return {
      tasks: [],
      editedTask: null,
    };
  },

  methods: {},
};
</script>

<template>
  <div class="container">
    <!-- using bootstrap table -->
    <table class="table table-bordered mt-5">
      <thead>
        <tr>
          <th scope="col">Task</th>
          <th scope="col">Type</th>
          <th scope="col" class="text-center">Edit</th>
          <th scope="col" class="text-center">Delete</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(task, index) in todos" :key="index">
          <td>{{ task.name }}</td>
          <td>
            {{ task.status }}
          </td>
          <td
            @click="$emit('editParams', index)"
            style="text-align: center; cursor: pointer"
          >
            <div>
              <img
                width="20"
                height="20"
                src="../components/icons/pen.png"
                alt="pen"
              />
            </div>
          </td>
          <td
            style="text-align: center; cursor: pointer"
            @click="$emit('deleteParams', index)"
          >
            <div>
              <img
                width="20"
                height="20"
                src="../components/icons/recycle.png"
                alt="delete"
              />
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
tr:nth-child(even) {
  background-color: #f2f2f2;
}
h2 {
  margin-top: 6rem;
  margin-bottom: 2rem;
}
.ItemCenter {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}
.pointer {
  cursor: pointer;
}
</style>
