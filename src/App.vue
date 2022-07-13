<template>
<!-- <Greet name="Andro" title="Programmer" />
<Greet name="Jean" title="Police" />
<Greet name="John" title="Analyst" />
<Greet :name="name" :title="channel" /> -->
<Article :title="'Article Title'" :likes="50" :isPublished="false" />
</template>

<script>
// import Greet from './components/Greet.vue'
import Article from "./components/Article.vue"
export default {
  name: 'App',
  components: {
    // Greet,
    Article
  },
  data() {
    return {
      name: 'vishwas',
      channel: 'Codevolution'
    }
  }
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
