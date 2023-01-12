<template>
    <div class="col-12 bg-dark">
        <p class="fs-5 fw-bold text-white">Found {{ store.cardsList.length }} cards</p>
    </div>
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