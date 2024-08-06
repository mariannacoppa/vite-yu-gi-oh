<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import DetailCard from './components/DetailCard.vue';
import FilterCards from './components/FilterCards.vue';
import { store } from './store';
import axios from 'axios';
export default {
  components: {
    AppHeader,
    CardsList,
    DetailCard,
    FilterCards
  },
  created() {
        this.getCards();
        this.getArchetypes();
    },
    methods: {
        getCards() {
            axios.get(store.apiUrl).then((response) => {
                store.cardsList = response.data.data;
                store.loading = false;
            });
        },
        getArchetypes() {
            axios.get(store.apiArchetypesUrl).then((response) => {
              for (let i = 0; i < 10; i++) {
                store.archetypesList.push(response.data[i]);
              }
            });
        }
    }
}
</script>
<template>
  <AppHeader />
  <main>
    <FilterCards />
    <CardsList />
    <DetailCard />
  </main>
</template>
<style lang="scss">
  @import './styles/generals.scss'
</style>