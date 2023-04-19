<script setup>

import card from './card.vue'
import {store} from '../store';
const values = ['Alien', 'Ally of Justice', 'Ancient Gear']


</script>

<template>
    <div class="container-fluid " :style="`background-color: ${store.color};` ">
        <select name="" id="" v-model="store.filter" @change="$emit('filter')">
            <option value="">all</option>
            <option :value="filter" v-for="filter in values">{{filter}}</option>
            <label for="">sdfsadfas</label>
            </select>
        <div class="container ms-color-white p-5">
            <div class="contatore d-flex align-items-center">
                <h3>FOUND {{ store.characters.length }} CARDS</h3>
            </div>
            <div class="cards d-flex flex-wrap  row row-cols-5 justify-content-center">
                <card :item="store.characters"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .ms-color-orange{
       background-color: #D48F38;
    }
    .ms-color-white{
        background-color: #fff;
        .contatore{
         background-color: #212529;
         height: 70px;
         width: 100%;
        color: #fff;
    }
    }
</style>