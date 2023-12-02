<script setup>
import { ref } from 'vue'
const header = ref('Yes')
const dingen = ref([
    {id: 1, label:'10 hoedjes'},
    {id: 2, label:'5 hoedjes'},
    {id: 3, label:'3 hoedjes'},
])
const newDing = ref("")
const newDingUrgent = ref(false)
</script>
<template>
    <h1>{{ header }}</h1>
    <form class="add-item-form"
        @submit.prevent="dingen.push({id: dingen.length + 1,label:newDing})"
    >
        <input 
            v-model.trim="newDing" 
            type="text" 
            placeholder="voeg toe"
        >
        <label>
            <input type="checkbox" v-model="newDingUrgent">
        </label>
        <button 
             
            class="btn btn-primary"
        >Save</button>
    </form>
    <ul>
    <li v-for="({id, label}, index) in dingen" :key="id">
        {{ label }}
    </li>
    </ul>
</template>