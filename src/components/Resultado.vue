<script setup>
const props = defineProps(['num1', 'num2', 'resultado'])
</script>

<template>
    <div class="text-center mt-5">
        <span v-if="props.num1 && props.num2 !=''"> 
        <h3>Resultado: {{ props.resultado }}</h3>
        </span>
        <span v-else-if="props.num1 || props.num2 === ''">
        <h3>Digite os números</h3>
        </span>
    </div>

</template>