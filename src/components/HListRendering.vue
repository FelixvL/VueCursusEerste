<script setup>
import { ref } from 'vue'
import { reactive } from 'vue'
import HLijstComponentOnderdeel from './HLijstComponentOnderdeel.vue'

 let a = 5
 //const items = ref([{ message: 'Foo', id:1}, { message: 'Bar',id:2 }])
 const items = reactive([{ message: 'Foo', id:1}, { message: 'Bar',id:2 }])
 const todos = reactive({isComplete:true,lijst:[{ name: 'fietsen' }, { name: 'lopen' }]})
 const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})
function changeSomething(){
    console.log("title anders");
    myObject.title = 'nieuwetitle'
    a = 9
    todos.isComplete = false
    todos.lijst[0].name = "biken"
    items.push({ message: 'HuppakeeItem', id:3}) // gaat kapot bij ref
    todos.lijst.push({ name: 'HuppakeeTodo', id:3})
}
</script>
<template>
<div>
    <button @click="changeSomething">klieik</button>
    <h1>{{a}}</h1>
    <li v-for="item in items">
        {{ item.message }}
    </li>
    <hr>
    <li v-for="(item, index) in items">
        {{ a }} - {{ index }} - {{ item.message }}
    </li>
    <hr>
    <li v-for="(item, index) of items">
        {{ a }} - {{ index }} - {{ item.message }}
    </li>
    <hr>
    <li v-for="(value, key, index) in myObject">
        {{ index }}. {{ key }}: {{ value }}
    </li>
    <hr>
    <p v-for="n in 10">{{ n }}</p>
    <hr>
    <ul>
        <template v-for="item in items">
            <li>{{ item.message }}</li>
            <li class="divider" role="presentation">opmerking</li>
        </template>
    </ul>
<hr>
    <template v-for="todo in todos.lijst">
    <li v-if="!todos.isComplete">
        {{ todo.name }} ---
    </li>
    </template>
<hr>
    <div v-for="item in items" :key="item.id">
        go<!-- content -->{{ item.id }} - {{ item.message }}
    </div>
<hr>
    <template v-for="todo in todos.lijst" :key="todo.name">
    <li>{{ todo.name }}</li>
    </template>
<hr>
    <HLijstComponentOnderdeel v-for="(item,index) in items" :key="item.id" :ding="item" :index="index"/>
<hr><hr><hr><hr><hr><hr><hr><hr><hr>
</div>
</template>