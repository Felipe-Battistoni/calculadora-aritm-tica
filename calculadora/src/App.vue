<template>
  <div id="app">
    <input type="number" v-model.number="num1" @input="calculate" placeholder="Número 1">
    <select v-model="operation" @change="calculate">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>
    <input type="number" v-model.number="num2" @input="calculate" placeholder="Número 2">
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: 'add',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operation) {
        case 'add':
          this.result = this.num1 + this.num2;
          break;
        case 'subtract':
          this.result = this.num1 - this.num2;
          break;
        case 'multiply':
          this.result = this.num1 * this.num2;
          break;
        case 'divide':
          this.result = this.num1 / this.num2;
          break;
      }
    }
  },
  watch: {
    num1: 'calculate',
    num2: 'calculate',
    operation: 'calculate'
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
input, select {
  margin: 10px;
  padding: 5px;
  font-size: 16px;
}
</style>
