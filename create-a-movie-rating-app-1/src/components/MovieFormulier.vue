<script setup>
const films = defineProps(['defilmen'])
function toevoegen(){
    films.defilmen.push(defilm)
}
const defilm = {}
</script>
<template>
    <div>
        hoi
        <hr>
        <button @click="toevoegen()" class="btn">klik</button>
        <hr>
        Naam:<input v-model="defilm.name" type="text">
        <hr>
        Description:<textarea v-model.number="defilm.description" type="number"></textarea>
        <hr>
        Rating:<input v-model.number="defilm.rating" type="number">
        <hr>
        Image:<input v-model.image="defilm.image" type="text">
        <hr>
        In Theaters:<input v-model.number="defilm.inTheaters" type="checkbox">
        

    </div>

</template>