<script setup>
import { ref, getCurrentInstance } from "vue";
import {state} from '../store.js'




const instance = getCurrentInstance();


const search = () => {
 
  instance.emit('search',state.searchTerm);
  
};
</script>

<template>
  <div>
    <h1>Search Movies Vue</h1>
    <form @submit.prevent="search">
      <input type="text" v-model="state.searchTerm" placeholder="Enter movie title" />
      <button type="submit">Search</button>
    </form>
  </div>
</template>

<style scoped>
input {
  width: 75vw;
  height: 50px;
  border-radius: 5px;
  border: none;
  margin-bottom: 10px;
}
button {
  border: none;
  color: white;
  height: 52px;
  width: 8vw;
  font-weight:bold ;
  background-color: rgb(243, 3, 3);
  padding: 4px;
  border-radius: 5px;
  cursor: pointer;
}
</style>
