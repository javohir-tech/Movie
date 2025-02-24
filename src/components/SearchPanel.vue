<template>
    <div class="mb-5 px-4 py-3 shadow rounded">
        <input v-model="searchQuery" @input="$emit('search-query' ,  searchQuery )" type="text" class="form-control mb-3 px-3 py-2" placeholder="Search">
        <FilterPanel/>
    </div>
</template>
<script>
import FilterPanel from './FilterPanel.vue';

export default {
    components:{
        FilterPanel
    },
    data(){
        return {
            searchQuery: ""
        }
    }
}
</script>
<style></style>