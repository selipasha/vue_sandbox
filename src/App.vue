<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal :header="header" :content="content" theme="dark" @close="toggleModal" />
  </div>
  <button @click="toggleModal">Open modal</button>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "My Vue App",
      header: "Sign up for the Giveaway",
      content: "Hoooray! You are a winner!",
      showModal: false
    };
  },
  methods: {
    toggleModal() {
     this.showModal = !this.showModal
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, sans-serif;
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
