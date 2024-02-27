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
.glow-on-hover {
  width: 220px;
  height: 50px;
  border: none;
  outline: none;
  color: #fff;
  background: #111;
  cursor: pointer;
  position: relative;
  z-index: 0;
  border-radius: 10px;
  margin-top: 10px;
  transition: 1s ease;
} 
.glow-on-hover:hover {
  transition: 1s ease;
  scale: 1.1;
}
.glow-on-hover:before {
  content: "";
  background: linear-gradient(
    45deg,
    #ff0000,
    #ff7300,
    #fffb00,
    #48ff00,
    #00ffd5,
    #002bff,
    #7a00ff,
    #ff00c8,
    #ff0000
  );
  position: absolute;
  top: -2px;
  left: -2px;
  background-size: 400%;
  z-index: -1;
  filter: blur(5px);
  width: calc(100% + 4px);
  height: calc(100% + 4px);
  animation: glowing 20s linear infinite;
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
  border-radius: 10px;
}
.glow-on-hover:active {
  color: #000;
  scale: 1.1;
}
.glow-on-hover:active:after {
  background: transparent;
}
.glow-on-hover:hover:before {
  opacity: 1;
}
.glow-on-hover:after {
  z-index: -1;
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  background: #111;
  left: 0;
  top: 0;
  border-radius: 10px;
}
@keyframes glowing {
  0% {
    background-position: 0 0;
  }
  50% {
    background-position: 400% 0;
  }
  100% {
    background-position: 0 0;
  }
}
</style>
