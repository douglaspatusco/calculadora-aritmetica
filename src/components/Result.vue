<script setup>
    const props = defineProps(['estado', 'operacao'])
</script>

<template>
    <span class="resultado d-block text-center my-5">{{ operacao ? operacao : 'Aguardando operação' }}</span>
</template>