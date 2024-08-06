<script>
import { store } from '../store';
import axios from 'axios';
import DetailCard from './DetailCard.vue';
import AppLoader from './AppLoader.vue';
export default {
    components: {
        DetailCard,
        AppLoader
    },
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
                store.loading = false;
            });
        }
    }
}
</script>
<template>
    <div>
        <div class="container">
            <AppLoader v-if="store.loading"/>
            <div class="row-list" v-else>
                <DetailCard v-for="card in store.cardsList" :key="card.id" :card="card"/>
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