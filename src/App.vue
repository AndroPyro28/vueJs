<template>
    <button @click="toggleModal = true">Open Modal</button>

    <Modal v-show="toggleModal" @closeModal="modalToggle"/>
</template>

<script>
import Modal from './components/Modal.vue'
export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      toggleModal: false
    }
  },
    methods: {
      modalToggle (name) {
        console.log(name)
        this.toggleModal = false;
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
