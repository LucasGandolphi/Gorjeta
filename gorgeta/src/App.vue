<template>
  <div class="container">
    <h1>Calculador De Gorgetas</h1>

    <input type="number" v-model="valor" placeholder="Valor à Pagar" />

    <select class="hud" name="Qualidade de serviço" v-model="gorgeta">
      <option value="1" selected="selected">
        Selecione a qualidade do serviço
      </option>
      <option value="1.05">5% Serviço Péssimo</option>
      <option value="1.10">10% Serviço Ruim</option>
      <option value="1.15">15% Serviço Ok</option>
      <option value="1.20">20% Serviço Bom</option>
      <option value="1.25">25% Serviço Muito bom</option>
      <option value="1.30">30% Serviço Excepcional</option>
    </select>

    <input
      type="number"
      placeholder="Quantidade de pessoas"
      v-model="pessoas"
    />

    <p>
      Gorjeta: R$
      {{ Math.ceil(((valor * gorgeta) / pessoas) * 100) / 100 }}
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";

const valor = ref("");
const pessoas = ref("");
const gorgeta = ref("");
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cormorant+Garamond&display=swap");

#app {
  max-width: 1280px;
  margin: 0 auto;
  height: 97vh;
  font-weight: normal;
  font-family: "Cormorant Garamond", serif;
}

.container {
  width: 50%;
  margin: auto;
  background-color: indigo;
  color: white;
  border-radius: 15px;
  padding: 5px;
}
</style>
