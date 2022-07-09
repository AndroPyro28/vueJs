<template>
  <!-- template is like react fragment  -->

  <h2 v-if="number < 0">The Number is Negative</h2>
  <h2 v-else-if="number === 0">The Number is Zero</h2>
  <h2 v-else-if="number > 0">The Number is Positive</h2>
  <h2 v-else>Not a number</h2>

  <template v-if="display">
    <h2>Andro Eugenio VueJs</h2>
  </template>

  <h2 v-show="showElement">Using V-show</h2>
  <!-- v-show only set display:none to css properties if the current condition is not truthy  -->

  <h2 v-if="showElement">Using V-show</h2>
  <!-- v-if  will completely inject to dom when condition is not truthy  -->

  <!-- <h2> // long term
    {{
      number < 0 
        ? `The number is negative`
        : number === 0
        ? `The number is zero`
        : ` The number is positive` 
    }}
    {{ number }} 
  </h2> -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      number: 0,
      display: true,
      showElement: false,
    };
  },
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
