<script setup>
import { ref } from 'vue'

const precio = ref(0)
const peso = ref(0)
const tipocambio = ref(0)

</script>

<template>
  <p>Peso:</p>
  <select v-model="peso">
    <option disabled value="">0</option>
    <option>5</option>
    <option>10</option>
    <option>15</option>
  </select>
    <p>Tipo de Cambio:</p>
	<input v-model="tipocambio" placeholder="Tipo de cambio" />
  <p>Precio de Etiqueta:</p>
	<input v-model="precio" placeholder="P.etiqueta" />
  <p>Calculos:</p>
  <p>Tax 7%: {{ (precio*0.07).toFixed(2) }}</p>
  <p>Peso: {{ peso }}</p>
  <p>Ganancia: {{ ((parseFloat(precio)+ parseFloat(peso)+parseFloat(precio*0.07))*0.25).toFixed(2) }}</p>
  <p>Total: {{ (parseFloat((parseFloat(precio)+ parseFloat(peso)+parseFloat(precio*0.07))*0.25) + parseFloat(precio) + parseFloat(precio*0.07) + parseFloat(peso)).toFixed(2) }}</p>
  <p>En Soles: {{ ((parseFloat((parseFloat(precio)+ parseFloat(peso)+parseFloat(precio*0.07))*0.25) + parseFloat(precio) + parseFloat(precio*0.07) + parseFloat(peso))*tipocambio).toFixed(2) }} </p>

</template>