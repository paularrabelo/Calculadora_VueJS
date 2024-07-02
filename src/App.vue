<script setup>
import {reactive} from 'vue'
import Cabecalho from './components/Cabecalho.vue'
import Formulario from './components/Formulario.vue'
import Operacao from './components/Operacao.vue'

const estado = reactive({
  num1: 0,
  num2: 0,
  resultado: '',
  operacao: 'soma',
})

const getSoma = () => {
  estado.resultado = parseFloat(estado.num1) + parseFloat(estado.num2)
  return estado.resultado
}

const getSubtracao = () => {
  estado.resultado = parseFloat(estado.num1) - parseFloat(estado.num2)
  return estado.resultado
}

const getMultiplicacao = () => {
  estado.resultado = parseFloat(estado.num1) * parseFloat(estado.num2)
  return estado.resultado
}

const getDivisao = () => {
  estado.resultado = parseFloat(estado.num1) / parseFloat(estado.num2)
  return estado.resultado
}

const getOperacao = () => {
  const { operacao } = estado

  switch (operacao) {
    case 'soma':
      return getSoma()
    case 'subtracao':
      return getSubtracao()
    case 'multiplicacao':
      return getMultiplicacao()
    case 'divisao':
      return getDivisao()
    default:
      return estado.resultado
  }
}

</script>

<template>
  <div class="container bg-light rounded-3">
    <Cabecalho />
    <Formulario :num1="evento => estado.num1 = evento.target.value" :num2="evento => estado.num2 = evento.target.value"/>
    <Operacao :resultado = "getOperacao()" :operacao="evento => estado.operacao = evento.target.value"/>

  </div>
</template>

<style scoped>

</style>
