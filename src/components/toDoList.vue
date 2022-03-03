<script setup>


 
</script>

<template>

    <div class="container">
        <h2>My ToDo App</h2>
        <div class="d-flex gap-2">
            <input type="text" placeholder="Enter Value" class="form-control">
            <button class="btn btn-warning rounded-1">submit</button>
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
                <tr>
                    <td>steal bananas from the store</td>
                    <td>To-do</td>
                    <td>
                        <div>
                            <span class="fa fa-pen"></span>
                        </div>
                    </td>
                    <td> </td>
                </tr>
            </tbody>
        </table>
    </div>


</template>

<style scoped>
    .ItemCenter{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
    }
</style>
