<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import DetailCard from './components/DetailCard.vue';
import axios from 'axios';
export default {
  components: {
    AppHeader,
    CardsList,
    DetailCard
  },
  
}
</script>
<template>
  <AppHeader />
  <main>
    <CardsList />
    <DetailCard />
  </main>
</template>
<style lang="scss">
  @import './styles/generals.scss'
</style>