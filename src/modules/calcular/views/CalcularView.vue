<template>
    <h3>Propiedades computadas</h3>
    <input type="text" v-model="valor">
    {{ valorCalculado }}
    <ResultadoSection  v-if="mostrarElemento" :resultado="valorCalculado"></ResultadoSection>
    <div v-else-if="isNaN(valor)">Este no es un Numero Valido</div>
    <div v-else>Aqui no se muestra nada</div>
</template>


<script setup>
import { ref, computed } from 'vue';
import ResultadoSection from '../components/ResultadoSection.vue';
const valor = ref('');
const valorCalculado = computed(()=>{
    return valor.value * 3
});


const mostrarElemento= computed(()=>{
    return valor.value >10;
})

</script>



<style scoped></style>