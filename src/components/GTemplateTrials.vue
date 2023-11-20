<script setup>
import { nextTick } from 'vue';
import { ref } from 'vue'
const msg = "fred"
let rawHTML = "<h1>eens kijken </h1>"
const nogeenid = "ditiddeidvaneendiv"
const nogeenid2 = "ditiddeidvaneendiv2"
let checkdezecss = ref("blauw");
async function doen(){
    document.getElementById(nogeenid).innerHTML = "hoi"
    document.getElementById(nogeenid2).innerHTML = "doei"
    checkdezecss = "groen";
    nextTick()
}
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
</script>
<style>
.blauw{
    background-color: blue;
}
.groen{
    background-color: green;
}
</style>
<template>
    <div>

        <h1>{{ msg }}</h1>
        <p> een {{ rawHTML }}</p>
        <p> een <span v-html="rawHTML"></span></p>
        <div v-bind:id="nogeenid"></div>
        <div :id="nogeenid2"></div>
        <button @click="doen">doen</button>
        <button :class="checkdezecss">Zomaar Gekkken Button{{ checkdezecss }}</button>
        <div v-bind="objectOfAttrs">ab</div>
        <hr><hr><hr><hr>
    </div>
</template>