<template>
    <header>
        <nav class="navbar bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand" href="#">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/11/Yu-Gi-Oh%21_%28Logo%29.jpg/1200px-Yu-Gi-Oh%21_%28Logo%29.jpg"
                        alt="Yu-gi-Oh Logo" class="img-fluid"> Yu-Gi-Oh Api</a>
            </div>
        </nav>
    </header>
</template>
<script>
export default {
    name: 'AppHeader',
}
</script>
<style lang="scss" scoped>
header {
    height: 80px;
    background-color: #FFFFFF;

    a {
        font-size: 2rem;
    }

    img {
        height: 40px;
    }
}
</style>