<script >
export default {
    props:{
        item: Object
    }
}
</script>

<template>
    <div class="col mb-4" v-for="(items, index) in item">
        <div class="card ms-height ">
            <img :src="items.card_images[0].image_url_small" alt="">
            <div class="card-body text-center">
                <h5 class="card-title">{{ items.name}}</h5>
                <p class="card-text"> {{ items.type }}</p>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .ms-height{
        height: 100%;
        background-color: #D48F38;
        h5{
            color: #fff;
        }
    }
</style>