<script setup>
import { ref } from "vue";
const nome = "Luiz";
const idade = "16";
const contador = ref(0);
// Função para inverter o texto
function inverter(texto) {
  return texto.split("").reverse().join("");
}
// Função para incrementar valor ao contador
function incrementar() {
  contador.value++;
}
// Função para diminuir valor do contador
function decrementar() {
  if (contador.value > 0) {
    contador.value--;
  }
}
// Função para zerar o contador
function reiniciar() {
  contador.value = 0;
}
// Armazenamento de valores da array quando for maior que 10
const numeros = ref([]);
// Repetição para que ocorra a identificação menor que 10
for (let i = 0; i < 10; i++) {
  numeros.value.push(i);
}
</script>
<template>
  <div class="info">
    <p class="itens topo">Nome: {{ nome }}</p>
    <p class="itens">Idade: {{ idade }} anos</p>
    <p class="itens">Nome invertido: {{ inverter(nome).toUpperCase() }}</p>
    <hr />
    <div class="buttons">
      <button class="glow-on-hover" @click="incrementar">+</button>
      <button class="glow-on-hover" @click="decrementar">-</button>
      <button class="glow-on-hover" @click="reiniciar">zerar</button>
    </div>
    <p class="valor-contador">Valor do contador: {{ contador }}</p>
    <div v-if="contador > 10" class="valor-maior-10">Valor maior que 10</div>
    <div v-else class="valor-menor-ou-igual-10">Valor menor ou igual a 10</div>
  </div>
</template>
<style scoped>
@import './assets/buttons.css';
.itens {
  display: flex;
  justify-content: center;
  align-items: center;
}
.topo {
  margin-top: 20px;
}
hr {
  width: 100%;
  margin: 20px 0;
}
.info {
  text-align: center;
  margin-top: 20px;
  background-color: rgba(41, 40, 40, 0.8);
  color: white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 30vw;
}
.teste {
  background-color: lightblue;
  padding: 5px;
  margin-top: 5px;
}
.valor-maior-10 {
  background-color: green;
  color: white;
  padding: 10px;
  margin-top: 10px;
  width: 100%;
}
.valor-menor-ou-igual-10 {
  background-color: red;
  color: white;
  padding: 10px;
  margin-top: 10px;
  width: 100%;
}
.valor-contador {
  font-size: 20px;
  margin: 10px;
}
</style>
