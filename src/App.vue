<template>
  
  <h3> {{name}} </h3>

  <ComponentB />
  
</template>

<script>
import ComponentB from './components/ComponentB.vue'
export default {
  name: 'App',
  components: {
    ComponentB
  },
  data() {
    return {
      name: 'Vishwas'
    }
  },
  provide() {
    return {
      username: this.name
    }
  },
    
}
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
