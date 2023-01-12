<template>
    <section class="col-12 bg-dark">
        <p class="fs-5 fw-bold text-white ms-3 mb-0">Found {{ store.cardsList.length }} cards</p>
    </section>
</template>
<script>
import { store } from '../store.js'
export default {
    data() {
        return {
            store,
        }
    },
}
</script>
<style lang="scss" scoped>

</style>