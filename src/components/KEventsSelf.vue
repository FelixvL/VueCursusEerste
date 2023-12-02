<script setup>
import {ref} from 'vue'
const teller = ref(0)
const naam = ref('Vue.js')
function doeGroetjes(event){
    alert(`Hello ${naam.value}`)
    if(event){
        alert(event.target.tagName)
    }
}
function zeggen(bericht){
    alert(bericht)
}
function waarschuwen(bericht, evenement){
    if(evenement){
        evenement.preventDefault()
    }
    alert(bericht)
}
function doedit(){
    console.log("doe dit");
}
function optoevoegen(){
    console.log("op toevoegen");
}
function enterdoen(){
    console.log('enter')
}
function spaceDoen(){
    console.log("space doen")
}
function altenter(){
    console.log("altenter")
}
function clickctrl(){
    console.log("clickctrl")
}
function onClick(){
    console.log("onClick")
}
function onCtrlClick(){
    console.log("ctrl click")
}
</script>

<template>
<div>
    <button @click="teller++">Add 1</button>
    <div>Teller: {{ teller }}</div>
    <button @click="doeGroetjes">Groeten Doen</button>
    <button @click="zeggen('hoi')">zeg hoi</button>
    <button @click="zeggen('doei')">zeg doei</button>
    <button @click="waarschuwen('dit gaan we niet doen',$event)">waarschuwen</button>
    <button @click="(event)=> waarschuwen('dit is de tweede:',event)">waarschuwen2</button>
    <a @click.stop="doedit">naar elders</a>
    <form @submit.prevent="optoevoegen"><input></form>
    <a @click.stop.prevent="doedit">tweede</a>
    <form @submit.prevent><input></form>
    <div @click.self="doedit"><button>Deze niet</button>maar ernaast wel</div>
    <div @click.capture="doedit">...</div>
    <a @click.once="doedit">linkje</a>
    <div @scroll.passive="doedit">...</div>
    <!-- only call `submit` when the `key` is `Enter` -->
    <input @keyup.enter="enterdoen" />
    <input @keyup.space="spaceDoen" />
    <input @keyup.alt.enter="altenter" />
    <input @click.ctrl="clickctrl">
    <button @click.ctrl="onClick">A</button>
    <button @click.ctrl.exact="onCtrlClick">A</button>
    <button @click.exact="onClick">A</button>

</div>
</template>