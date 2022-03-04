<script>
    export default {
        name: 'ToDoList',
        props: {
            msg: String,
        },
        data() {
            return {
                task: '',
                tasks: [
                   
                ],
            }
        },
        methods: {
            submitTask() {
                if (this.task.length === 0) {
                    return;
                }
                this.tasks.push({
                    name: this.task,
                    status: 'to-do',
                });
            }
        }
    }

 
</script>

<template>

    <div class="container">
        <h2>My ToDo App</h2>
        <div class="d-flex gap-2">
            <input v-model="task" type="text" placeholder="Enter Value" class="form-control">
            <button @click="submitTask" class="btn btn-warning rounded-1">submit</button>
        </div>
        <!-- using bootstrap table -->
        <table class="table table-bordered mt-5">
            <thead>
                <tr>
                    <th scope="col">Task</th>
                    <th scope="col">Status</th>
                    <th scope="col" class="text-center">#</th>
                    <th scope="col" class="text-center">#</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(task, index) in tasks" :key="index">
                    <td>{{task.name}}</td>
                    <td>{{task.status}}</td>
                    <td style="text-align: center;">
                        <div>
                            <img width="20" height="20" src="../components/pen.png" alt="pen">
                        </div>
                    </td>
                    <td style="text-align: center;"> 
                        <div>
                            <img width="20" height="20" src="../components/recycle.png" alt="pen">
                        </div>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>


</template>

<style scoped>
    h2{
        margin-top: 6rem;
        margin-bottom: 2rem;
    }
    .ItemCenter{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
    }
</style>
