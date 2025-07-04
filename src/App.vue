<script setup>
import { ref } from "vue";
import AddName from "./components/AddName.vue";
import NameList from "./components/NameList.vue";

// Estado reactivo para la lista de nombres
const nombres = ref([]);

// Función que se ejecuta cuando el hijo emite un nuevo nombre
const agregarNombre = (nuevoNombre) => {
  if (nuevoNombre.trim() !== "") {
    nombres.value.push(nuevoNombre.trim());
  }
};
</script>

<template>
  <h1>Gestor de Nombres</h1>
  <!-- Componente para ingresar nombres -->
  <AddName
    titulo="Agregar un nuevo nombre"
    @nombre-agregado="agregarNombre"
  />

  <!-- Componente que muestra la lista -->
  <NameList :nombres="nombres" />
</template>

<style scoped>
h1 {
  text-align: center;
  margin-bottom: 1rem;
}
</style>