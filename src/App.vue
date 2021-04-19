<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"><img> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <h1>{{title}}</h1>
  <input type="text" ref="name">
  <button @click="handleClick">click me</button>
  <p id="empty">
  </p>
  <div v-if="showModal">
    <Modal 
      :header='header'
      :text='text' 
      theme='dark'
      @close="toggleModal"
    />
  </div>
  <button @click.right="toggleModal">open modal</button>
</template>


<script>
import HelloWorld from './components/HelloWorld.vue';
import Modal from './components/Modal.vue';


export default {
  name: 'App',
  data() {
    return {
      title: 'Welcome to your Vue',
      header: 'Sign up or head out',
      text: 'Your name here',
      showModal: false
    }
  },
  components: {
    Modal
  },
  methods: {
    handleClick() {
      document.getElementById('empty').innerHTML = this.$refs.name;
      this.$refs.name.classList.add('active')
      this.$refs.name.focus();
      this.title.classList.add('active')
    },
    toggleModal() {
      this.showModal = !this.showModal 
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

  h1{
    border-bottom: 1px solid black;
    padding-bottom: 10px;

  }

  .active {
    color: red;
  }
</style>
