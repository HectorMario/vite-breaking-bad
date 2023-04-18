<script setup>
import navInfo from './components/header.vue'; 
import cards from './components/main.vue'
import {store} from './store';
import axios from "axios";


  axios.get(`${store.apiURL}`)
  .then((resp) => {
      store.characters = resp.data.data;
      store.number = resp.data
    })

  function   funtionFilter() {   
      const params = {
        ...store.filter && { archetype: store.filter }  
      }
      axios.get(`${store.apiURL}`, {
        params
      }).then(resp => {
        store.characters = resp.data.data;
      }).catch(error => {
        
      }).finally(() => {
      })
    }
</script>

<template>
 <navInfo />
 <cards @filter="funtionFilter"/>
</template>

<style lang="scss">
  @use './styles/general.scss'
</style>
