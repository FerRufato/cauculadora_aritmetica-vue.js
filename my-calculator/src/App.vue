<script setup>
import { ref, computed } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');

const resultado = computed(() => {
  switch (operacao.value) {
    case '+':
      return numero1.value + numero2.value;
    case '-':
      return numero1.value - numero2.value;
    case '*':
      return numero1.value * numero2.value;
    case '/':
      return numero2.value !== 0 ? numero1.value / numero2.value : 'Erro Divisão por zero';
    default:
      return 0;
  }
});
</script>

<template>  
 <div class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-group">
      <input
        type="number"
        v-model.number="numero1"
        placeholder="Digite o primeiro número"
      />
      <select v-model="operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input
        type="number"
        v-model.number="numero2"
        placeholder="Digite o segundo número"
      />
    </div>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</template>

<style scoped>
.calculator {
  max-width: 400px;
  margin: 0 auto;
  text-align: center;
}

.input-group {
  display: flex;
  justify-content: center;
  margin-bottom: 20px;
}

input[type="number"] {
  width: 100px;
  margin: 0 10px;
}

select {
  margin: 0 10px;
}
</style>

