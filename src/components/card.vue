<script >
import { store } from '../store';
export default {
    props:{
        item: Object
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="col mb-4" v-for="(items, index) in item">
        <div class="card ms-height " :style="`background-color: ${this.store.color};` ">
            <img :src="items.card_images[0].image_url_small" alt="">
            <div class="card-body text-center ">
                <h5 class="card-title">{{ items.name}}</h5>
                <p class="card-text"> {{ items.type }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .ms-height{
        height: 100%;
        h5{
            color: #fff;
        }
        .card-text{
            vertical-align: baseline;
        }
    }
</style>