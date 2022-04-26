<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{ black: theme = 'dark' }">
      <h1>{{ header }}</h1>
      <p>{{ content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "content"],
  methods: {
    closeModal() {
      this.$emit('close')
    }
  }
};
</script>

<style scoped>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  text-align: center;
}

.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

.modal h1 {
  color: #03cfb4;
  border: none;
}

.modal p {
  font-family: normal;
}

.black {
  background: #000;
  color: #fff;
}
</style>
