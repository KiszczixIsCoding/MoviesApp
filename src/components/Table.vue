<template>
      <div class="container">
        <table class="table table-bordered">
            <thead class="thead-dark">
                <tr>
                    <th scope='col'>Title</th>
                    <th scope='col'>Production year</th>
                    <th scope='col'>Cast</th>
                    <th scope='col'>Genres</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="movie in movies.slice(0, displayIndex)" v-bind:key="movie.title">
                    <th scope='row'>{{movie.title}}</th>
                    <td>{{movie.year}}</td>
                    <td>{{movie.cast.join(', ')}}</td>
                    <td>{{movie.genres.join(', ')}}</td>
                </tr>
            </tbody>
        </table>
        <div>
          <button v-on:click="decrement()" id="button1" type="button" class="btn btn-outline-primary">Show less</button>
          <button v-on:click="increment()" id="button2" type="button" class="btn btn-outline-primary">Show more</button>
        </div>
      </div>
</template>

<script>
import Movies from '../assets/movies.json';
//import _ from 'underscore';


export default {
  name: 'Table',
  data: 
    function() {
      return {
          movies: Movies,
          displayIndex: 10
      }
  },
  created: function() {
    //console.log("po przefiltrowaniu")
    this.emitter.on('filtered_films', (filtered_films)=>{
      this.movies = filtered_films;
    })
   // console.log("po przefiltrowaniu wielkosc: " + _.size(this.movies));
  },
  mounted: function() {
    //console.log("wysylamy do przefiltrowania")
    this.emitter.emit('emitted_table', this.movies)
    this.emitter.emit('table_to_filter_by_genre',this.movies)
  
  },
  methods: {
    increment: function() {
      if (this.displayIndex < Movies.length) {
        this.displayIndex += 10
      }
    },
    decrement: function() {
      if (this.displayIndex > 10) {
        this.displayIndex -= 10
      }
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
#button1 {
  margin: 15px 45px 35px 80px;
  float: left;
} 
#button2 {
  margin: 15px 80px 15px 45px;
  float: right;
}

</style>
