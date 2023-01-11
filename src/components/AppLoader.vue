<template>
    <div class="coin"></div>
</template>
<script>
export default {

}
</script>
<style lang="scss">
.coin {
    height: 470px;
    width: 320px;
    animation:
        spin 2s linear infinite,
        change 3s infinite linear .5s;
    background-size: cover;
    margin: 2rem auto;
}

@keyframes change {

    0%,
    33.33% {
        background-image: url("../assets/img/front.png");
    }

    33.34%,
    66.66% {
        background-image: url("../assets/img/back.png");
    }

    66.67%,
    100% {
        background-image: url("../assets/img/front.png");
    }
}

@keyframes spin {
    100% {
        transform: rotateY(360deg);
    }
}
</style>