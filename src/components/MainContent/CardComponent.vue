<template>
    <div class="col-6 col-md-3 col-lg-2 d-flex">
        <div class="card text-bg-dark mb-3">
            <img :src="backImage" @mouseover="backImage = frontImage" class="card-img-top" :alt="cardInfo.name">
            <div class="card-body">
                <h6 class="card-title text-center text-danger">{{ cardInfo.name }}</h6>
                <p class="card-text text-center fw-lighter">{{ cardInfo.archetype }}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'CardComponent',
    props: [
        "cardInfo"
    ],
    data() {
        return {
            frontImage: this.cardInfo.card_images[0].image_url,
            backImage: this.getImagePath('back.png')
        }
    },
    methods: {
        getImagePath: function (img) {
            return new URL((`../../assets/img/${img}`), import.meta.url).href;
        }
    }
}
</script>
<style lang="scss" scoped>

</style>