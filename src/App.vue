
<template>
  <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="calculator">
      <input type="number" v-model.number="number1" @input="calculate" placeholder="Número 1">
      <select v-model="operation" @change="calculate">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="number2" @input="calculate" placeholder="Número 2">
      <p>Resultado: {{ result }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      number1: 0,
      number2: 0,
      operation: '+',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case '+':
          this.result = this.number1 + this.number2;
          break;
        case '-':
          this.result = this.number1 - this.number2;
          break;
        case '*':
          this.result = this.number1 * this.number2;
          break;
        case '/':
          this.result = this.number1 / this.number2;
          break;
      }
    }
  },
  mounted() {
    this.calculate();  
  }
};
</script>

<style>
#app {
  font-family: 'Roboto', sans-serif;
  text-align: center;
  margin-top: 50px;
}

* {
  background-color: #ffe6db;
  
}
.calculator {
  display: inline-block;
  text-align: left;
  padding: 20px;
  
  background-color: #ffe6db;
}

input, select {
  display: block;
  margin: 10px 0;
  padding: 10px;
  font-size: 16px;
  background-color:#ffe6db;
  
}
</style>
