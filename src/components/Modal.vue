<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{dark: theme === 'dark'}">
       <h1>{{header}}</h1>
       <p>{{text}}</p>
    </div>
  </div>
</template>

<script>

export default { 
  props: [ 
    'header',
    'text', 
    'theme'
  ],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
}
</script>



<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

h1{
  color: tomato; 
}

.modal.dark {
  color:white;
  background: rgba(255, 0, 0,0.6);
}

.modal.dark {
  color:white;
  background: rgba(8, 0, 0, 0.6);
}

.modal.dark h1 {
  color:white;
}

</style>