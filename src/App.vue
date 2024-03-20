<script setup>
import Search from "./components/Search.vue";
import {state} from './store'
import {computed} from 'vue'


const movies = computed(()=>{
  return state.data
})

// console.log(movies);
</script>

<template>
  <div>
    <Search @search="state.handleSearch" />

    <div v-if="movies">
      <ul>
        <li v-for="movie in movies" :key="movie.imdbID">
          <img :src=movie.Poster alt="Movie Poster" width="100">
          <h3><span>Title:</span> {{ movie.Title }}</h3>
          <p><span>Year:</span> {{ movie.Year }}</p>

        </li>
      </ul>

    </div>
    <p v-else>Loading...</p>
  </div>
</template>

<style scoped>
ul{
  list-style-type: none;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
li{
  width: 300px;
  height: 500px;
  margin: 10px;
  padding:20px 10px 10px 10px;
  background-color: rgb(247, 5, 5);
  border-radius: 50px;
  transition: all ease-in-out 0.5s;
}
img{
  width: 250px;
  height: 350px;
  margin: 10px;
  border-radius: 25px;

}

li:hover{
  transform: scale(1.1);
  filter: sepia(100%);
span{
  color: whitesmoke;
}
}

h3, p {
  color: white;
  line-height: 2rem;
  
  
}

span{
  color: rgb(12, 12, 12);
  text-align: left;
}



</style>
