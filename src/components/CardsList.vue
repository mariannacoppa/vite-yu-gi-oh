<script>
import { store } from '../store';
import axios from 'axios';
export default {
    data() {
        return{
            store,
        }
    },
    created() {
        this.getCards()
    },
    methods: {
        getCards() {
            axios.get(store.apiUrl).then((response) => {
                store.cardsList = response.data.data;
            });
        }
    }
}
</script>
<template>
    <div>
        <div class="container">
            <div class="row-list">
                <div class="col-20" v-for="card in store.cardsList" :key="card.id">
                    <div class="card">
                        <img :src="card.card_images[0].image_url" alt="">
                        <div class="card-body">
                            <h6>
                                {{ card.name }}
                            </h6>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
    .row-list {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
    .col-20 {
        width: calc(100% / 5);
    }
    .card {
        background-color: burlywood;
        margin: 10px;
        img {
            max-width: 100%;
        }
    }
</style>