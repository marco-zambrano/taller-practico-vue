<template>
    <div>
        <h2>{{ titulo }}</h2>
        <input v-model="nombre" type="text" placeholder="Escribe un nombre" />
        <button @click="emitirNombre">Agregar</button>
    </div>
</template>

<script setup>
import { ref } from "vue";
import { defineProps, defineEmits } from "vue";

const props = defineProps({
    titulo: String,
});

const emit = defineEmits(["nombre-agregado"]);

const nombre = ref("");

const emitirNombre = () => {
    if (nombre.value.trim() !== "") {
        emit("nombre-agregado", nombre.value);
        nombre.value = "";
    }
};
</script>

<style scoped>
input {
    margin-right: 0.5rem;
    padding: 0.4rem;
}
button {
    padding: 0.4rem 0.8rem;
    cursor: pointer;
}
</style>
