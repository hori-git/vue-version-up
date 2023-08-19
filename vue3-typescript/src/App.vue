<script setup lang="ts">
import { ref } from 'vue'

const message = ref('')
const showConfirmation = ref(false)

const toggleConfirmation = () => {
  showConfirmation.value = !showConfirmation.value
}
</script>

<template>
  <div id="app">
    <!-- 入力画面 -->
    <div v-if="!showConfirmation">
      <input v-model="message" />
      <button @click="toggleConfirmation">確認</button>
    </div>

    <!-- 確認画面 -->
    <div v-if="showConfirmation">
      <p>入力したメッセージ: {{ message }}</p>
      <button @click="toggleConfirmation">戻る</button>
    </div>
  </div>
</template>

<style scoped>
#app {
  font-family: 'Arial', sans-serif;
  width: 300px;
  margin: 50px auto;
  padding: 20px;
  border: 1px solid #ddd;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
}

input {
  padding: 8px;
  margin-bottom: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

button {
  padding: 8px 15px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #0056b3;
}

p {
  margin-bottom: 10px;
}
</style>
