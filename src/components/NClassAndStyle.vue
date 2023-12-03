<script setup>
import { ref } from 'vue'
import { reactive } from 'vue'
import { computed } from 'vue'
const isActive=ref(true)
const hasError = ref(true)
const klasseObject = reactive({
  ene: true,
  andere: true
})
const getal1 = 3
const getal2 = 5
const berekendobject = computed(()=>({
  hoog: getal1 == 3 && getal2 == 5
}))
const aClass = ref('hoog')
const bClass = ref('static')
const eneV = 'ene'
</script>
<style scoped>
  .hoog{
    background-color: blueviolet;    
  }
  .actief{
    background-color: red;
  }
  .static{
    border:  2px solid blue;
    
  }
  .text-danger{
    color:orange;
  }
  .ene{
    background-color: orange;
  }
  .andere{
    color:blue;
  }
</style>
<template>
  <div>
    <div :class="{actief:isActive}">Hoi</div>
    <div class="static" :class="{actief:isActive, 'text-danger':hasError}">Hoi</div>
    <div :class="klasseObject">Hoi</div>
    <div :class="berekendobject">Hoi</div>
    <div :class="[aClass, bClass]">Doen</div>
    <div :class="[{ andere: isActive }, eneV]">Maken</div>
  </div>
</template>