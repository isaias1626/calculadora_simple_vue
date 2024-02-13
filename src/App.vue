<script setup>
  import { ref, computed } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operator = ref('add');

const resultado = computed(() => {
  switch (operator.value) {
    case '+':
      return num1.value + num2.value;
    case '-':
      return num1.value - num2.value;
    case '*':
      return num1.value * num2.value;
    case '/':
      return num1.value / num2.value;
    default:
      return 0;
  }
});

</script>
<template>
  <div class="container">
    <div class="title">
      <h1>Calculadora Simple</h1>
    </div>
    <div class="form">
      <p class="resultad">Insira os Valores Abaixo</p>
      <input v-model="num1" type="number" name="campo1">
      <select v-model="operator" name="selector">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">x</option>
        <option value="/">/</option>
      </select>
      <input v-model="num2" type="number" name="campo2">
      <p class="resultad">Resultado:{{ resultado }}</p>
    </div>
  </div>
</template>

<style scoped>
  .container {
    width: 100%;
    justify-content: center;
  }

  h1 {
    text-align: center;
    color: white;
  }

  .title {
    background-color: #851B54;
    padding: 50px;
    margin: 0 auto;
    margin-top: 30px;
    border-radius: 10px;
    max-width: 500px;
  }

  .form {
    text-align: center;
    background-color: #851B54;
    padding: 50px;
    margin: 50px auto;
    border-radius: 10px;
    display: block;
    max-width: 500px;
  }

  .resultad {
    text-align: center;
    color: #fff;
    font-size: 20px;
    font-weight: 800;
  }

  input {
    margin: 5px;
    border-radius: 10px;
    border: solid 2px white;
  }
</style>
