<script setup>
import navInfo from './components/header.vue'; 
import cards from './components/main.vue'
import {store} from './store';
import axios from "axios";

  axios.get(`${store.apiURL}`)
  .then((resp) => {
      const myData = resp.data.data;
      store.characters = myData
      store.number = resp.data
    })

</script>

<template>
 <navInfo />
 <cards/>
</template>

<style lang="scss">
  @use './styles/general.scss'
</style>
