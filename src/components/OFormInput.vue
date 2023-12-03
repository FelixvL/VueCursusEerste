<script setup>
import { ref } from 'vue'

const header = ref('Shopping List App')
const items = ref([
   {
     id: 1, 
     label: "10 party hats", 
   },
   {
		id: 2, 
    label:"2 board games", 
   },
   {
     id: 3, 
     label: "20 cups", 
   }
])
const nieuwItem = ref("")
const eengetal = ref(9)
const newItemPriority = ref("low")
const hp = ref(true)
const smaken = ref([])
const elbericht = ref("")
const hetbericht = ref("")
const geselecteerd = ref("")
const geselecteerdM = ref([])
</script>

<template>
  	<h1>{{ header }}</h1>
    <input 
      v-model="nieuwItem"
 			type="text" 
      placeholder="Add an item"
    >
    <input 
      v-model.lazy="nieuwItem"
 			type="text" 
      placeholder="Add an item"
    >
    <input 
      v-model.trim="nieuwItem"
 			type="text" 
      placeholder="Add an item"
    >
    <input 
      v-model.number="eengetal"
 			type="text" 
      placeholder="Add an item"
    >
    <input type="radio" v-model="newItemPriority" value="low">Low
    <input type="radio" v-model="newItemPriority" value="high">High
    <input type="checkbox" v-model="hp">hp:{{ hp }}
    {{ newItemPriority }}
    --{{ nieuwItem }}--
    {{ eengetal + eengetal }}
    <input type="checkbox" v-model="smaken" value="choco">Choco
    <input type="checkbox" v-model="smaken" value="fraise">Fraise
    <input type="checkbox" v-model="smaken" value="vanilla">Vanilla
    {{ smaken }}
  <ul>
    <li 
      v-for="({id, label}, index) in items" :key="id"
    >
      {{label}}
    </li>
  </ul>
  <hr><hr>
  <p>Message is: {{ elbericht }}</p>
  <input v-model="elbericht">
  <span>Multiline message is:</span>
<p style="white-space: pre-line;">{{ hetbericht }}</p>
<textarea v-model="hetbericht" placeholder="add multiple lines"></textarea>
<div>Selected: {{ selected }}</div>

<select v-model="geselecteerd">
  <option disabled value="">Please select one</option>
  <option>A</option>
  <option>B</option>
  <option>C</option>

</select>
{{ geselecteerd }}
<select v-model="geselecteerdM" multiple>
  <option disabled value="">Please select one</option>
  <option>A</option>
  <option>B</option>
  <option>C</option>

</select>
{{ geselecteerdM }}
</template>