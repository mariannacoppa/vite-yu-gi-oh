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
        ciao
    </div>
</template>
<style lang="">
    
</style>