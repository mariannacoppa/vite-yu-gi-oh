<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue';
import DetailCard from './components/DetailCard.vue';
export default {
  components: {
    AppHeader,
    CardsList,
    DetailCard
  }
}
</script>
<template>
  <div>
    <AppHeader />
    <CardsList />
    <DetailCard />
  </div>
</template>
<style lang="scss">
  @import './styles/generals.scss'
</style>