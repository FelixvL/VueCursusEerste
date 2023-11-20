<script>
import { ref } from 'vue'

export default{
    setup(){
        let hoi = ref(24)
        function verhogen(somegetal){
            // this.hoi += 3 // werkt ook
            console.log(somegetal);
            hoi.value += 5
        }
        return {
            hoi,
            verhogen
        }
    }
}
</script>

<template>
    <div>
        <h1>Doen</h1>
        <h2>{{ hoi }}</h2>
        <button @click="hoi++">{{ hoi }}</button>
        <button @click="verhogen(17)">Met Twee</button>
        <hr><hr><hr>
    </div>
</template>