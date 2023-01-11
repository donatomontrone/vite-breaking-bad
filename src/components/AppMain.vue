<template>
    <main class="m-3">
        <div class="container">
            <div class="row g-3">
                <div class="col-12 bg-dark">
                    <p class="fs-5 fw-bold text-white">Found {{ store.cardsList.length }} cards</p>
                </div>
                <div class="col-6 col-md-3 col-lg-2 d-flex" v-for=" card in store.cardsList">
                    <div class="card text-bg-dark mb-3">
                        <img :src="card.card_images[0].image_url" class="card-img-top" :alt="card.name">
                        <div class="card-body">
                            <h6 class="card-title text-center text-danger">{{ card.name }}</h6>
                            <p class="card-text text-center fw-lighter">{{ card.archetype }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </main>
</template>
<script>
import { store } from '../store.js';
export default {
    name: "AppMain",
    data() {
        return {
            store
        };
    },

}
</script>
<style lang="scss" scoped>
main {
    height: calc(100% - 80px);

}
</style>