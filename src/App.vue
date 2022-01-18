<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1> 
    {{ title }}
  </h1>
  <p>welcome ....</p>
  <!-- <input type="text" ref="name">
  <button @click="handleClick" > Click me </button> -->

  <div v-if="showModal">
  <Modal :header="header" :text="text" theme='sale' @close="toggleModal"/>
  </div>
  <button @click="toggleModal">open modal</button>
  </template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data () {
    return{
      title: `* My First Vue App *`,
      header:"sign up for the give away",
       text:" get ready",
       showModal: false,
    }
  },
  methods: {
    handleClick(){
      console.log(this.$refs.name)
      this.$refs.name.classList.toggle(`active`)
      this.$refs.name.focus()
    },
    toggleModal(){
      this.showModal = !this.showModal
    }
  },
  // components: {
  //   HelloWorld
  // }
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

h1{
  text-transform: capitalize;
  font-size: 5rem;
}

.modal.sale{
  background: crimson;
  color: white;
}

.modal.sale h1{
  color: white;
}
</style>
