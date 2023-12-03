<script setup>
defineProps(['defilm'])
function doen(i, tebewerkenfilm){
    console.log(i)
    console.log(tebewerkenfilm)
    if(tebewerkenfilm.rating == i){
      alert("al gestemd");
    }else{
      tebewerkenfilm.rating = i
    }
    console.log("we gaan doen");
}
</script>

<style scoped>


.poster {
  flex: 0 0 auto; /* Do not grow or shrink, respect the width */
  margin: 10px;
/*  max-width: calc(100% - 20px); /* Adjust the 20px to your actual margin size */
max-width: 300px; /* Adjust the 20px to your actual margin size */
justify-content: space-between; 
height: 200px; 
}

.star {
  color: darkgrey;
}
.poster img {
  width: auto; /* Adjust width automatically */
  max-height: 450px; /* Make sure the image does not exceed the container's height */
  object-fit: contain; /* Ensures the image aspect ratio is maintained */
}
.categorie{
    background-color: blue;
    color:white;
    padding:3px;
    border-radius: 5px;
    margin: 5px;
}

</style>

<template>
        <!-- Assume v-for is used here to iterate over a list of films -->
        <div class="poster" >
            <img :src="defilm.image" >
            <h1><b>{{ defilm.name }}</b></h1>
            <span class="categorie" v-for="genre in defilm.genres">{{ genre }}</span>
            <div class="omschrijving">
                <div>{{ defilm.description }}</div>
                <div>
<!--                    De rating <span class="star" v-for="index in defilm.rating" :key="index">X{{ index }}</span>
                    <hr>-->
                    De rating: <span  v-for="teller in 5" @click="doen(teller, defilm)">
                        <span v-if="defilm.rating >= teller" class="star">X</span>
                        <span v-else>X</span>
                    </span>
                    
                </div>
            </div>
        </div>

</template>
