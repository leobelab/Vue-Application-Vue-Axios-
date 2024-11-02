<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p> 

  <teleport to="#modals" v-if="showModal">
      <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">sign un now</a>
          <a href="#">more info</a>
        </template>
        <h1>Ninja Giveaway!</h1>
        <p>Grab your ninja sway for half price!</p>
      </Modal>
  </teleport>

  <teleport to="#modals" v-if="showModalTwo">
      <Modal @close="toggleModalTwo">
        <h1>Sign up to the newsletter!</h1>
        <p>For updates and promo codes!</p>
      </Modal>
  </teleport>

  <button @click="toggleModal">open modal 1</button>
  <button @click="toggleModalTwo">open modal 2</button>
</template>
<!-- because there are different templates for different components
    and we see some of them and not others at different moment -->

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App', //Component name
  components: {
    Modal
  },
  data() {
    return {
      title: 'My First Vue App :)',
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
#app, #modals {
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


<!--
<template>
<input type="text" ref="name">
  <button @click="handleClick">click me</button>
<template>

methods: {
    handleClick() {
      console.log(this.$refs.name)
      this.$refs.name.classList.add('active')
      this.$refs.name.focus()
    }
  }
  -->