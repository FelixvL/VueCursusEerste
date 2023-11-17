<script>
export default{
    data(){
        return{
            header : 'Yes',
            newItem : '',
            dingen:[
                {id: 1, label:'10 hoedjes'},
                {id: 2, label:'5 hoedjes'},
                {id: 3, label:'3 hoedjes'},
            ]
        }
    },
    mounted(){
        this.header = 'hoi'
    },
    methods:{
        opslaan(){
            this.header = 'opgeslagen'
            this.dingen.push({id:this.dingen.length + 1, label:this.newItem})
            this.newItem = ''
        }
    }
}
</script>
<template>
 <div>
    <h1>{{header}}</h1>
    <input 
        @keyup.enter = "dingen.push({id:dingen.length +1, label:newItem})"
        type="text" v-model="newItem" placeholder="Add an Item"
    >
    <button @click="dingen.push({id:dingen.length +1, label:newItem})">save</button>
    <button @click="opslaan">save2viamethods</button>
    <ul>
        <li v-for="ding in dingen" :key="ding.id">{{ding.label}}</li> 
    </ul>
 </div>
</template>
