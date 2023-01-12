<template>
    <section class="bg-dark pt-3">
        <div class="container">
            <div class="row">
                <div class="col-3 offset-4">
                    <select class="form-select-sm" v-model="userInput" v-on:change="$emit('selectedInput', userInput)">
                        <option selected value="chaos">Chaos</option>
                        <option value="cyber dragon">Cyber Drago</option>
                        <option value="blue-eyes">Occhi Blu</option>
                        <option value="dark magician">Mago Nero</option>
                    </select>
                </div>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: 'SelectComponents',
    data() {
        return {
            userInput: ''
        }
    },
}
</script>
<style lang="scss" scoped>

</style>