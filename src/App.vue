<script setup>
import { reactive } from 'vue';

const aritmetica = reactive({
  operacoes: '+',
  valor1: 0,
  valor2: 0,
  resultado: 0
});

const calcular = () => {
  const { operacoes, valor1, valor2, resultado } = aritmetica;

  switch (operacoes) {
    case 'somar':
      return resultado = parseFloat(valor1) + parseFloat(valor2);
    case 'sub':
      return resultado = parseFloat(valor1) - parseFloat(valor2);
    case 'mult':
      return resultado = parseFloat(valor1) * parseFloat(valor2);
    case 'divid':
      if (valor2 == 0) {
        return resultado = undefined;
      };
      return resultado = parseFloat(valor1) / parseFloat(valor2);
  };
};

</script>

<template>
  <div class="container d-flex flex-column justify-content-center align-items-center w-50 bg-light">
    <header>
      <h1 class="mb-5">
        Calculadora Aritmética
      </h1>
    </header>
    <form class="d-flex flex-column justify-content-center align-items-center">
      <input
        :value="aritmetica"
        class="mb-2"
        type="number"
      />
      <select @change="evento => aritmetica.operacoes = evento.target.value" class="form-control mb-2">
        <option selected value="somar">+</option>
        <option value="sub">-</option>
        <option value="mult">*</option>
        <option value="divid">/</option>
      </select>
      <input
        :value="aritmetica"
        class="mb-2"
        type="number"
      />
    </form>
    <p>{{ aritmetica.resultado }}</p>
  </div>
</template>

<style scoped>
.form-control {
  width: 20%;
}
</style>