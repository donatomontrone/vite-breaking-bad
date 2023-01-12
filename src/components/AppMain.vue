<template>
    <main class="mt-3">
        <div class="container" v-if="isLoading">
            <div class="row">
                <div class="col-12">
                    <AppLoader />
                </div>
            </div>
        </div>
        <div class="container" v-else>
            <div class="col-12 bg-dark">
                <p class="fs-5 fw-bold text-white">Found {{ store.cardsList.length }} cards</p>
            </div>
            <div class="row g-2">
                <AppCards v-for="cardElement in store.cardsList" :cardInfo="cardElement" />
            </div>
        </div>
    </main>
</template>
<script>
import { store } from '../store.js';
import AppCards from './AppCards.vue';
import AppLoader from './AppLoader.vue';
export default {
    name: "AppMain",
    components: {
        AppCards,
        AppLoader
    },
    data() {
        return {
            store,
            isLoading: true,
        }
    },
    methods: {
        stopLoader() {
            this.isLoading = false;
        }
    },
    created() {
        setTimeout(this.stopLoader, 3000);
    }
}
</script>
<style lang="scss" scoped>
main {
    background-image: url(https://preview.redd.it/zlprsrsjpbf61.png?auto=webp&s=692301b1538e06081ef45417980c1499fb8d9454);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: calc(100% - 60px);
}
</style>