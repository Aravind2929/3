<template>
 <h1>{{ title }}</h1>
 <p> Welcome... </p>
   <div v-if="showModal">
    <teleport to=".modals" @close="toggleModals">
      <template v-slot:links>
        <a href='#'> sign up now </a>
        <a href='#'> more info </a>
      </template>
   <h1> Giveaway </h1>
   <p> Welcome to the Modal World </p>
   </teleport>
   </div>

     <div v-if="showModalTwo">
    <Modal @close="toggleModalsTwo">
   <h1> Sign up to the newsletter </h1>
   <p> For updates & promo codes! </p>
   </Modal>
   </div>

   <button @click.shift="toggleModal"> Open Modall </button>
   <button @click="toggleModalTwo"> Open Modal </button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App',
      showModal: false,
      showModalTwo: false,
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
.modal h1 {
  border-bottom: 1px solid #dddd;
  display: inline-block;
  padding-bottom: 15px;
}
.modal p {
  font-style: normal;
  color: white;
}
.modal .actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: #333;
}
.modal .actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.modal sale {
  background: crimson;
  color: white;
}
.modal.sale h1 {
  color: white;
}
.modal.sale .actions {
  color: white;
}
.modal.sale .actions a {
  color: white;
}
</style>
