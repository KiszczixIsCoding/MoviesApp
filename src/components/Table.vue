<template>
  <div class="table">
      <table>
          <thead>
            <th>Title</th>
            <th>Production year</th>
            <th>Cast</th>
            <th>Genres</th>
          </thead>
          <tbody>
            <tr v-for="movie in movies" v-bind:key="movie">
                <td>{{movie.title}}</td>
                <td>{{movie.year}}</td>
                <td>{{movie.cast.join(', ')}}</td>
                <td>{{movie.genres.join(', ')}}</td>
            </tr>
          </tbody>
      </table>
  </div>
</template>

<script>
import Movies from '../assets/movies.json'

export default {
  name: 'Table',
  data: function() {
      return {
          movies: Movies
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
