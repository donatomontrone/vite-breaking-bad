<template>
    <main>
        <div class="row">
            <p v-for="item in store.cardsList"> {{ item.name }}</p>
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

</style>