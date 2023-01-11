<template>
    <main class="m-3">
        <div class="container">
            <div class="row g-3">
                <div class="col-12 bg-dark">
                    <p class="fs-5 fw-bold text-white">Found {{ store.cardsList.length }} cards</p>
                </div>
                <div class="col-6 col-md-3 col-lg-2" v-for=" card in store.cardsList">
                    <div class="card">
                        <img :src="card.card_images[0].image_url" class="card-img-top" alt="...">
                        <div class="card-body">
                            <p class="card-text">Some quick example text to build on the card title and make up the bulk
                                of the card's content.</p>
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