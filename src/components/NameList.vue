<template>
    <div>
        <h2>Lista de nombres</h2>
        <ul>
            <li v-for="(nombre, index) in nombres" :key="index">{{ nombre }}</li>
        </ul>
    </div>
</template>

<script setup>
import { defineProps } from "vue";

const props = defineProps({
    nombres: Array,
});
</script>

<style scoped>
ul {
    list-style-type: none;
    padding-left: 0;
}
li {
    padding: 0.3rem 0;
    border-bottom: 1px solid #ccc;
}
</style>
