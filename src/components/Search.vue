<template>
    <div class="container">
    <form>
        <div class="form-group">
            <label for=inputTitle>Tytuł</label>
            <input type="text" id=inputTitle class="form-control" placeholder="Podaj tytuł lub fragment tytułu filmu"/>
        </div>
        <div class="form-group row">
          <label class="col-sm-4 col-form-label" for="inputProductionFrom">Rok produkcji od:</label>
          <div class="col-sm-8">
              <input type="text" id=inputProductionFrom class="form-control"  placeholder="Liczba naturalna z przedziału 1900-2019"/>
          </div>
        </div>
        <div class="form-group row">
            <label class="col-sm-4 col-form-label" for="inputProductionTo">Rok produkcji do:</label>
            <div class="col-sm-8">
                <input type="text" id=inputProductionTo class="form-control" placeholder="Liczba naturalna z przedziału 1900-2019"/>
            </div>
        </div>
        <div class="form-group">
          <label for="inputCast">Obsada</label>
          <input type="text" id="inputCast" class="form-control" placeholder="Imię i nazwisko"/>
        </div>
        <div class="form-group row">
            <input type="button" class="btn btn-info col-sm-12" value="Szukaj"/>
        </div>
    </form>
    </div>
</template>

<script>
//import Movies from '../assets/movies.json'

export default {
  name: 'Search',
//   data: function() {
//       return {
//           movies: Movies
//       }
//  }
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
th {
  vertical-align: center;
}
</style>
