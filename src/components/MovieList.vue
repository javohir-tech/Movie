<template>
    <div class="mb-5 px-4 py-3 shadow rounded">
        <ul class="list-group list-group-flush">
            <MovieListItem v-for="(movie, index)
                in movies" :movie="movie" @toggle-favorite="toggleFavorite" @toggle-like="toggleLike"
                @toggle-delete="toggleDelete" />
        </ul>
    </div>
</template>
<script>
import MovieListItem from './MovieListItem.vue';

export default {
    components: {
        MovieListItem
    },
    props: {
        movies: {
            type: Array,
            required: true
        }
    },
    methods: {
        toggleFavorite(kino) {
            kino.favorite = !kino.favorite
        },
        toggleLike(kino) {
            kino.like = !kino.like
        },
        toggleDelete(kino) {
            this.$emit('delete-movie', kino)
        }
    }
}
</script>
<style></style>