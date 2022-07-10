<template>
  <!-- <h2 v-for="(name, index) in names" :key="index" >{{index}} {{name}}</h2> iterating in array of string -->

  <!-- <h2 v-for="(name, index) in fullnames" :key="index" >{{name.first}} {{name.last}}</h2>  iterating in array of objects --> 

  <!-- <div v-for="(actor, index) in actors" :key="index" >
    <h2> {{index + 1}}. {{actor.name}} </h2>
    <h2 v-for="(movie, index) in actor.movies" :key="index" > * {{movie}}</h2> iterating in array of objects with array props
  </div> -->

  <!-- <h2 v-for="(value, key, index) in myInfo" :key="index">{{key}} {{value}}</h2>  iterating with object with key and values -->

  <template  v-for="(name, index) in names" :key="index"  >  
    <h2 v-show="name === 'andro'">{{index}} {{name}}</h2>
  </template>
  
</template>

<script>
export default {
  name: "App",
  data() {
    return {
     names: ['andro', 'jean', 'john' ],
     fullnames: [
      {
        first: 'andro', last: 'eugenio'
      },
      {
        first: 'jean', last: 'correa'
      },
      {
        first: 'john', last: 'doe'
      },
     ],
     actors: [
      {
        name: 'andro eugenio',
        movies: ['ang provinsyano', 'john wick']
      },
      {
        name: 'jean correa',
        movies: ['once upon a time', 'horror']
      },
      {
        name: 'john doe',
        movies: ['hotdog', '007']
      },
     ],
     myInfo: {
      name: "andro",
      channel: 'androPyro',
      course: 'vue 3'
     }
    };
  },
  methods: {
    
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
