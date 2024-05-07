<template>
  <div class="container">
    <h1 class="header">Hai, Hello, Annyeong!</h1>
    <div class="form-group">
      <input type="text" class="form-control input-field" id="text" v-model="text" placeholder="Ketik apa saja"><br>
    </div>

    <div class="button-group">
      <button class="btn btn-dark" @click="toggleTextStyle">Bold</button> &nbsp;
      <button class="btn btn-dark" @click="toggleTextColor">Change color</button> &nbsp;
      <button class="btn btn-dark" @click="increaseFontSize">Font size +1</button> &nbsp;
      <button class="btn btn-dark" @click="decreaseFontSize">Font size -1</button>
    </div>

    <p :style="{ 
      color: bluetext ? 'blue' : 'black',
      'font-weight': boldtext ? 'bold' : 'normal',
      'font-size': fontSize + 'px' 
    }">{{ text }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const text = ref('');
const bluetext = ref(false);
const boldtext = ref(false);
const fontSize = ref(14)

function toggleTextStyle() {
  boldtext.value = !boldtext.value;
}

function toggleTextColor() {
  bluetext.value = !bluetext.value;
}

function increaseFontSize() {
  fontSize.value += 1;
}

function decreaseFontSize() {
  fontSize.value -= 1; 
}
</script>

<style>
body {
  background-color: #85a2e0;
}
.container {
  padding: 20px;
  margin: 150px auto;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 8px;
}

.header {
  text-align: left;
  color: #333;
}

.form-group {
  margin-bottom: 20px;
}

.input-field {
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

.button-group {
  text-align: center;
}

.btn {
  transition: background-color 0.3s ease; 
}

.btn:hover {
  background-color: #333;
  color: #fff;
}
</style>
