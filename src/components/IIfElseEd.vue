<script setup>
    import { ref } from 'vue'
    import { reactive } from 'vue'
    let awesome = ref(true)
    let qq = reactive({a:'A'})
    function changeit(){
        console.log("in switch")
        switch(qq.a){
            case 'A':
                console.log("het was a")
                qq.a='B'
                break
            case 'B':
            qq.a='C'
                break
            case 'C':
            qq.a='D'
                break
            case 'D':
            qq.a='A'
                break
            default:
            console.log("het was default")
            qq.a ='B'
        }
    } 
</script>
<template>
    <div>
        I else
        <h1 v-if="awesome">Vue is awesome!</h1>
        <hr><hr>
        <button @click="awesome = !awesome">Toggle</button>
        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no 😢</h1>
        <hr><hr>
        <button @click="changeit">verander</button>
        <div v-if="qq.a === 'A'">
            A
            </div>
            <div v-else-if="qq.a === 'B'">
            B
            </div>
            <div v-else-if="qq.a === 'C'">
            C
            </div>
            <div v-else>
            Not A/B/C
        </div>
    </div>
</template>