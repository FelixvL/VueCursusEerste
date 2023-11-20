<script>
import { nextTick } from 'vue';
export default{
    data(){
        return{
            ding1: 2,
        }
    },
    methods:{
        async doortellen(){
            this.ding1++
            await nextTick(this.jojo())
        },
        jojo(){
            console.log("go");
        }
    }
}
</script>
<template>
    <div>So lets go {{ ding1 }}
        <button id="counter" @click="doortellen">{{ ding1 }}</button>
        <hr><hr><hr>
    </div>
</template>