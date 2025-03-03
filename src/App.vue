<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';

const aritmetica = reactive({
  operacoes: 'somar',
  valor1: 0,
  valor2: 0,
  resultado: 0
});

function defineValor1(e) {
  aritmetica.valor1 = e.target.value;
  if (aritmetica.valor1 == '') {
    aritmetica.valor1 = 0;
  };
  aritmetica.valor1 = parseFloat(aritmetica.valor1);
  calcular();
};

function defineValor2(e) {
  aritmetica.valor2 = e.target.value;
  if (aritmetica.valor2 == '') {
    aritmetica.valor2 = 0;
  };
  aritmetica.valor2 = parseFloat(aritmetica.valor2);
  calcular();
};

function trocarOperador(e) {
  aritmetica.operacoes = e.target.value;
  calcular();
};

const calcular = () => {
  const { operacoes, valor1, valor2 } = aritmetica;

  switch (operacoes) {
    case 'somar':
      return aritmetica.resultado = parseFloat(valor1) + parseFloat(valor2);
    case 'sub':
      return aritmetica.resultado = parseFloat(valor1) - parseFloat(valor2);
    case 'mult':
      return aritmetica.resultado = parseFloat(valor1) * parseFloat(valor2);
    case 'divid':
      if (valor2 == 0) {
        return aritmetica.resultado = undefined;
      };
      return aritmetica.resultado = parseFloat(valor1) / parseFloat(valor2);
  };
};

</script>

<template>
  <section class="calc d-flex flex-column justify-content-center align-items-center">
    <div class="container d-flex flex-column justify-content-center align-items-center w-50">
      <Cabecalho />
      <Calculadora :valor-um="defineValor1" :troca-operador="trocarOperador" :valor-dois="defineValor2" />
      <p class="text-center">
        <b>Resultado:</b>
        <br />
        {{ aritmetica.resultado }}
      </p>
    </div>
  </section>
</template>

<style scoped>
* {
  font-family: "Press Start 2P", system-ui;
}

.calc {
  height: 100vh;
  background-color: #000;
}

.container {
  border: 3px solid #000;
  border-radius: 10px;
  padding: 1rem;
}

p {
  margin-top: 1rem;
  font-size: 2rem;
  color: #fff;
}

</style>