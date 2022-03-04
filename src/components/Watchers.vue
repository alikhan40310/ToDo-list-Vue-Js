<script>
    export default {
        name: 'watchers',
        data() {
            return {
                volume: 0,
            }
        },
        methods: {

        },
        watch: {
            volume(newValue, oldValue) {
                if(newValue > oldValue && newValue === 16) {
                    alert('16 is the max');
                }
                
            }
        }
    }
</script>

<template>
    <div class="container">
        <h2>Volume tracker (0-20)</h2>
        <h3>current volume = {{volume}}</h3>
        <div  class="">
            <button class="btn btn-primary m-2" @click="volume +=2">Increase</button>
            <button class="btn btn-primary " @click="volume -=2">Decrease</button>
        </div>
    </div>
</template>