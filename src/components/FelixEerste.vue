<script>
export default{
    data(){
        return{
            teller : 1,
            header : 'Yes',
            newItem : '',
            dingen:[
                {id: 1, label:'10 hoedjes'},
                {id: 2, label:'5 hoedjes'},
                {id: 3, label:'3 hoedjes'},
            ],
            uiterobject:{
                innerobject:{tellertje:0},
                lijst:['mooi','lelijk']
            }
        }
    },
    mounted(){
        this.header = 'hoi'
        this.ophogen()
    },
    methods:{
        gelaagd(){
            this.uiterobject.innerobject.tellertje++
            this.uiterobject.lijst.push('ertussenin')
        },
        ophogen(){
            this.teller++
        },
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
    <h1>{{header}} ({{teller}})</h1>
    <input 
        @keyup.enter = "dingen.push({id:dingen.length +1, label:newItem})"
        type="text" v-model="newItem" placeholder="Add an Item"
    >
    <button @click="dingen.push({id:dingen.length +1, label:newItem})">save</button>
    <button @click="opslaan">save2viamethods</button>
    <button @click="ophogen">ophogen</button>
    <button @click="gelaagd">nested dingen</button>
    <ul>
        <li v-for="ding in dingen" :key="ding.id">{{ding.label}}</li> 
    </ul>
    <h2>{{uiterobject.innerobject.tellertje}}</h2>
    <div v-for="soep in uiterobject.lijst"><h1>yes</h1><span>{{soep}}</span></div>
    <hr><hr><hr>
 </div>
</template>
