<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: '+',
      resultado: 0
    }
  },
  methods: {
    calcular() {
      // Defina a variável "resultado" com base nos valores de "num1", "num2" e "operacao"
      switch (this.operacao) {
        case '+':
          this.resultado = parseFloat(this.num1) + parseFloat(this.num2)
          break
        case '-':
          this.resultado = parseFloat(this.num1) - parseFloat(this.num2)
          break
        case '*':
          this.resultado = parseFloat(this.num1) * parseFloat(this.num2)
          break
        case '/':
          this.resultado = parseFloat(this.num1) / parseFloat(this.num2)
          break
      }
    }
  }
}
</script>

<template>
  <header>
    <div class="">
      <h1>Calculadora</h1>
    </div>
  </header>
  <div>
    <label for="num1">Número 1:</label>
    <input type="number" id="num1" v-model="num1" @input="calcular">
    <label for="num2">Número 2:</label>
    <input type="number" id="num2" v-model="num2" @input="calcular">
    <label for="operacao">Operação:</label>
    <select id="operacao" v-model="operacao" @change="calcular">
      <option value="+">Adição</option>
      <option value="-">Subtração</option>
      <option value="*">Multiplicação</option>
      <option value="/">Divisão</option>
    </select>
  </div>
  <div>
    <label for="resultado">Resultado:</label>
    <input type="text" id="resultado" :value="resultado" disabled>
  </div>
</template>

<style>
* {
  padding: 20px;
}

label {
  display: inline-block;
  width: 100px;
}

input {
  margin-right: 16px;
}

input[type="number"],
select {
  width: 200px;
  padding: 5px;
  margin-bottom: 10px;
  font-size: 16px;
}

input[type="text"] {
  width: 200px;
  padding: 5px;
  font-size: 16px;
  color: #333;
  border: none;
  background-color: #f8f8f8;
}
</style>

