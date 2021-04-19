<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"><img> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">click me</button>
  <p id="empty"></p>
  <!-- div to disply modal -->
  <div v-if="showModal">
    <!-- modal -->
    <Modal :header="header" :text="text" theme="dark" @close="toggleModal">
      <H1>Giveaway</H1>
      <p>Half price</p>
    </Modal>

    <template  >
      <a href="#">sign up</a>
      <a href="#">slow down</a>
    </template>
  </div>

  <!-- div to disply modal2 -->
  <div v-if="showModal2">
    <!-- modal2 -->
    <Modal :header="header" :text="text" @close="toggleModal2">
      <H1>Sign to Newsletter</H1>
      <p>For updates and promo codes</p>
    </Modal>
  </div>

  <button @click.right="toggleModal">open Giveaway</button>
  <button @click.right="toggleModal2">open Newsletter</button>
</template> 
 

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  data() {
    return {
      title: "Welcome to your Vue",
      header: "Sign up or head out",
      text: "Your name here",
      showModal: false,
      showModal2: false,
    };
  },
  components: {
    Modal,
  },
  methods: {
    handleClick() {
      document.getElementById("empty").innerHTML = this.$refs.name;
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
      this.title.classList.add("active");
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
    },
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

button{
  padding: 10px 20px;
  outline: none;
  margin-left: 20px;
  border-radius: 12px;
  border: none;
  background-color: cyan;
  color: white;
  font-size: 24px;

}

h1 {
  border-bottom: 1px solid black;
  padding-bottom: 10px;
}

.active {
  color: red;
}
</style>
