<template>
    <main class="pt-3">
        <div class="container" v-if="store.cardsList.length === 0">
            <div class="row">
                <div class="col-12">
                    <LoaderComponent />
                </div>
            </div>
        </div>
        <div class="container" v-else>
            <div class="row g-2">
                <CardsList />
            </div>
        </div>
    </main>
</template>
<script>
import { store } from '../../store.js';
import CardsList from './CardsList.vue';
import LoaderComponent from './LoaderComponent.vue';
export default {
    name: "AppMain",
    components: {
        CardsList,
        LoaderComponent
    },
    data() {
        return {
            store,
        }
    },
}
</script>
<style lang="scss" scoped>
main {
    background: rgb(163, 106, 2);
    background: linear-gradient(180deg, rgba(163, 106, 2, 1) 41%, rgba(92, 51, 6, 1) 88%);
}
</style>