<template>
   <card-my class="movie-list list-grop">
        <!-- <movie-list-itme  
          v-for="movie in muviesYubor" 
          :key="movie.id"  
          :movieProps="movie"
          @onLike="onLike2(movie)"
          /> -->
       <movie-list-itme  
          v-for="movie in muviesYubor" 
          :key="movie.id"  
          :movieProps="movie"
          @onToggle="$emit('onToggle', $event)"
          @onRemove="$emit('onRemove', movie.id)"
          />
   </card-my>
</template>

<script>
import MovieListItme from '../movie-list-itme/MovieListItme.vue';
export default {
  components: { MovieListItme },
    name: 'Vue3SaMovieList',
    props: {
      muviesYubor: {
        type: Array,
        required: true
      }
    },
    // methods: {
    //   onLike2(movie){
    //       this.$emit('onLike3', movie)
    //       // console.log(this.movieProps.id);
    //     }
    // },

  };
</script>
