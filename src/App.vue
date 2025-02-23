<template>
  <div class="container">
    <div class="content">
      <AppInfo />
      <SearchPanel />
      <MovieList :movies="movies" @delete-movie="deleteMovie"/>
      <MovieAddForm />
    </div>
  </div>
</template>
<script>
import AppInfo from './components/AppInfo.vue';
import MovieAddForm from './components/MovieAddForm.vue';
import MovieList from './components/MovieList.vue';
import SearchPanel from './components/SearchPanel.vue';

export default {
  components: {
    AppInfo,
    SearchPanel,
    MovieList,
    MovieAddForm
  },
  data() {
    return {
      movies: [
        {
          name: "Taxtlar O'yini",
          viewers: 1232,
          like: false,
          favorite: true
        },
        {
          name: "Titanlar Hujumi",
          viewers: 123,
          like: false,
          favorite: false
        },
        {
          name: "Intersteller",
          viewers: 1022,
          like: true,
          favorite: false
        },
      ]
    }
  },
  methods:{
    deleteMovie(kino){
      this.movies = this.movies.filter(film => film !==  kino)
    }
  }

}
</script>
<style></style>