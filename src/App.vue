<template>
  <h2>methods {{ fullname }}</h2>
  <h2>computed {{ firstname }} {{ lastname }}</h2>
  <button @click="changeName('jean correa')">change name</button>
  <button @click="someValue += 1">{{ someValue }}</button>

  <h2>Volume {{ volume }}</h2>
  <button @click="volume += 1">Increase volume</button>
  <button @click="volume -= 1">Decrease volume</button>
  <button @click="someArray.push('...')" >Add ....</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      someValue: 0,
      firstname: "andro",
      lastname: "eugenio",
      volume: 0,
      someArray: []
    };
  },

  methods: {
    changeName(value) {
      this.fullname = value;
    },
  },

  computed: {
    // computed will only rerender when the data value changed if its not change it will only use its cached value
    fullname: {
      get() {
        return `${this.firstname} ${this.lastname}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstname = names[0];
        this.lastname = names[1];
      },
    },
  },

  watch: {
    volume: {
      handler(newValue, oldValue) {
        if( oldValue < newValue && newValue === 16) {
          alert('volume may damage your hearing')
        }
      },
      immediate: true,
    },
    someArray: {
      handler(newValue, oldValue) {
      console.log('someArray', {newValue, oldValue});
      },
      immediate: true,
      deep: true
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
