<script>
import { store } from '../store.js';
export default {
    data() {
        return {
            store
        }
    }
}
</script>
<template>
    <div>
        <select name="" id="" class="select-control p-2 ms-5">
            <option value="">Seleziona Archetipo</option>
            <option :value="archetype.archetype_name" v-for="(archetype, index) in store.archetypesList">{{ archetype.archetype_name }}</option>
        </select>
    </div>
</template>
<style lang="scss">
    
</style>