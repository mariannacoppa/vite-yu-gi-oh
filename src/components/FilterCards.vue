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
        <select name="" id="" class="form-control">
            <option value="">Seleziona Archetipo</option>
            <option :value="archetype.archetype_name" v-for="(archetype, index) in store.archetypesList">{{ archetype_name }}</option>
        </select>
    </div>
</template>
<style lang="scss">
    
</style>