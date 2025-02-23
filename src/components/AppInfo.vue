<template>
    <div class="my-5 px-4 py-3 rounded shadow">
        <p class="fs-3">Barcha Kinolar: {{ AllMovies }}</p>
        <p class="fs-3">Mashhur Kinolar: {{ FavoratieMovies }}</p>
    </div>
</template>
<script>
export default {
    props:{
        AllMovies :{
            type:Number,
            required: true
        },
        FavoratieMovies:{
            type: Number,
            required: true
        }
    }
}
</script>
<style>
    
</style>