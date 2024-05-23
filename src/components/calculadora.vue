<template>
  <div class="container p-5 mt-5 mb-5 bg-light">
    <input type="number" v-model="numero1" @input="calcularResultado">
    <select v-model="operacao" @change="calcularResultado">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="numero2" @input="calcularResultado">
    <div>Resultado: {{ resultado }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          this.resultado = parseFloat(this.numero1) + parseFloat(this.numero2);
          break;
        case '-':
          this.resultado = parseFloat(this.numero1) - parseFloat(this.numero2);
          break;
        case '*':
          this.resultado = parseFloat(this.numero1) * parseFloat(this.numero2);
          break;
        case '/':
          this.resultado = parseFloat(this.numero1) / parseFloat(this.numero2);
          break;
        default:
          this.resultado = 0;
      }
    }
  }
};
</script>
