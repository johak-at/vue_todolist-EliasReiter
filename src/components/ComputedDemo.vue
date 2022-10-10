<script setup>
import { computed } from "@vue/reactivity";
import { ref } from "vue";

let number = ref(5);
let number_quadrat = computed(function () {
    return number.value * number.value;
});



</script>

<template>
    <h1>ComputedDemo!</h1>
    <p>Zahl: {{ number }}</p>
    <p>Quadriert: {{ number_quadrat}}</p>
</template>