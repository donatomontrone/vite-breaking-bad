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
import { store } from '../store.js';
import axios from 'axios';
export default {
    name: 'AppHeader',
    data() {
        return {
            store,
            apiUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0",
        }
    },
    methods: {
        getCard() {
            axios.get(this.apiUrl, {
                params: {
                }
            })
                .then((response) => {
                    this.store.cardsList = (response.data.data);
                })
        }
    },
    created() {
        this.getCard();
    }
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