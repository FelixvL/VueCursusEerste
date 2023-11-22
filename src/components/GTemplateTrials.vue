<script setup>
import { nextTick } from 'vue';
import { ref } from 'vue'
const msg = "fred"
let getal = 5
let choice = true
let seen = ref(false)
let rawHTML = "<h1>eens kijken </h1>"
const nogeenid = "ditiddeidvaneendiv"
const nogeenid2 = "ditiddeidvaneendiv2"
let checkdezecss = ref("blauw");
let naardewebsite = "http://nos.nl"
let gebeurtenis = "mouseover"
async function doen(){
    document.getElementById(nogeenid).innerHTML = "hoi"
    document.getElementById(nogeenid2).innerHTML = "doei"
    checkdezecss = "groen";
    
    seen=true
    nextTick()
}
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
function gaatdoenalles(){
    getal++
    return "dit is uit functie: "+getal++
}
function ditgaatnugebeuren(){
    console.log("dit gaat nu gebeuren");
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
        {{ getal+1 }}<br>
        {{ choice ? 'Yes' : 'No' }}<br>
        {{ msg.split('').reverse().join('') }}
        <p v-if="seen">now you see mee</p>
        <span>{{ gaatdoenalles() }}</span>
        <h1>{{ msg }}</h1>
        <p> ee n {{ rawHTML }}</p>
        <p> een <span v-html="rawHTML"></span></p>
        <div v-bind:id="nogeenid"></div>
        <div :id="nogeenid2"></div>
        <button @click="doen">doe!n</button>
        <button :class="checkdezecss">Zomaar Gekkken Button{{ checkdezecss }}</button>
        <div v-bind="objectOfAttrs">ab</div>
        <a v-bind:href="naardewebsite" target="_blank"> klikken </a>
        <a :href="naardewebsite" target="_blank"> klikken2 </a>
        <a href="http://nos.nl" target="_blank"> cjecl </a>
        <button v-on:click="ditgaatnugebeuren">nugebeuren</button>
        <button @click="ditgaatnugebeuren">nugebeuren</button>
        <button v-on:[gebeurtenis]="ditgaatnugebeuren">dynamische klik</button>
        <button @[gebeurtenis]="ditgaatnugebeuren">dynamische klik</button>
        <hr><hr><hr><hr>
    </div>
</template>