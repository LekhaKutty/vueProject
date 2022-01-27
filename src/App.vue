<template>
  <h1>{{title}}</h1>
  <h6>Welcome ...</h6>
  <br>
  <div v-if="showModal"> 
    <Modal @passToggleModalfromApp="toggleModal">
      <template v-slot:linksToModal>
        <a href="#">Sign up now!</a>
        <br>
        <br>
        <br>
        <a href="#">Click for more INFO!</a>
      </template> 
      <h1>My First Vue App</h1>
      <p>SignUp for the give away!</p>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <br>
  <div v-if="showModalTwo"> 
    <Modal @passToggleModalfromApp="toggleModalTwo">
      <template v-slot:linksToModal>
        <a href="#">Sign out now!</a>
      </template> 
      <h1>This is the second Modal using the same component</h1>
      <p>Lets check how it will works....</p>
    </Modal>
  </div>
  <button @click="toggleModalTwo">Open Modal Two</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App :)',
      header: "SignUp for the give away!",
      text: "Grab Item",
      showModal: false,
      showModalTwo: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
