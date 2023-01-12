<template>
    <CardComponent v-for="cardElement in store.cardsList" :cardInfo="cardElement" />
</template>
<script>
import { store } from '../../store.js'
import CardComponent from './CardComponent.vue'
export default {
    name: "CardsList",
    components: {
        CardComponent,
    },
    data() {
        return {
            store,
        }
    },
}
</script>
<style lang="scss" scoped>

</style>