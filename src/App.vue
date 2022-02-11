<template>
  <h1>abdullah bin masood -ASE </h1>
  <!-- component 1 -->

  <div v-if="showModal">
    <Modal :title="title" :header="header" :text="text"  theme="dark" @close="toggleModal">

      <p style="color:red">This is a sample paragraph for <b style="color:yellow">SLOTS in Vue</b>. Thanks!!</p>
      <template v-slot:links >
        <div >
          <p>Example of Named Slots</p>
          <a class="navigation-links" target="_blank" href="https://www.google.com">Google</a> 
          <a class="navigation-links" target="_blank" href="https://www.youtube.com">Youtube</a> 
        </div>      
      </template>
    </Modal>  
  </div>

  <!-- SECOND MODAL  -->
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1 style="color:black">This is Second Modal</h1>
      <p style="color:blue">Hello World!!</p>
    </Modal>

  </div>

  <div style="margin-top:15%">
    <button @click="toggleModal">Open First Modal</button>
    <button @click="toggleModalTwo">Open Second Modal</button>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'
      
export default {
  name: 'App',
  components: {Modal},
  data(){
    return{
    title:"Vue App",
    header:"Signup to header part",
    text:"A quick brown fox jumps over the lazy dog",
    showModal:true,
    showModalTwo:false,
  }
  },
  methods: {
    toggleModal(){
      this.showModal=!this.showModal

    },
    toggleModalTwo(){
      this.showModalTwo=!this.showModalTwo

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
  color: #365e3b;
  margin-top: 60px;
}
.navigation-links{
  border: 2px solid rgb(131, 212, 123);
  width: 100px;
  padding: 3px;
  margin: 10px 10px;
  color: rgb(70, 201, 77);
  text-decoration: none;
}

</style>
