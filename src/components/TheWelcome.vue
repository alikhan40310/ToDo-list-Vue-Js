<script >
    export default {
        data() {
            return {
                value: '',
                deleteTable:'',
                ninjas: [
                    {
                        name: 'Ryu',
                        age: 25,
                        belt: 'black',
                    },
                    {
                        name: 'Yoshi',
                        age: 32,
                        belt: 'green',
                    },
                    {
                        name: 'Crystal',
                        age: 16,
                        belt: 'pink',
                    },

                    
                ],
            }
        },
        methods: {
            deleteNinja: function(index) {
                this.ninjas.pop();
            },
            deleteData(){
                // delete table data
                this.ninjas=[];
            }, 
        },
        // life cycle hooks
        created() {
            console.log('Component is created!');
        },
        beforeCreate() {
            console.log('Component is about to be created!');
        },
        beforeMount() {
            console.log('Component is about to be mounted!');
        },
        mounted() {
            console.log('Component is mounted!');
        },
        beforeUpdate() {
            console.log('Component is about to be updated!');
        },
        updated() {
            console.log('Component is updated!');
        },
        beforeMount() {
            console.log('Component is about to be destroyed!',document.getElementById('demo'));
        },
        mounted() {
            console.log('Component is destroyed!',document.getElementById('demo'));
        },
        

    
    }
</script>

<template>
    <div class="container">
    <h1 id="demo">its a heading</h1>

      <table class="table table-striped">
          <tbody class="">
              <tr  v-for="ninja in ninjas" :key="ninja">
                <td>{{ ninja.name }}</td>
                <td>{{ ninja.age }}</td>
                <td>{{ ninja.belt }}</td>
              </tr>
          </tbody>
          <button class="btn btn-primary" @click="deleteData">click here</button>
      </table>
    </div>
</template>
