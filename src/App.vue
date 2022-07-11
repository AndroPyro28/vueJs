<template>
  <h2>{{name}}</h2>
    <button @click="changeName($event, 'jean')" draggable="true"  >Change name</button>
      <h2>{{count}}</h2>
    <button @click="setCount('incremeant')"> + </button>
  <button @click="setCount('decremeant')"> -</button>
  <button @click="setCount('decremeant')"> -</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: 'andro',
      count: 0
    };
  },
  methods: {
    changeName (event, nameparams) {
      console.log(event)
      this.name = nameparams
    },
    setCount (action, number=1) {
      if(action == "incremeant") return this.count += number;
      if(action == "decremeant") return this.count -= number;

      return this.count;
    },
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
