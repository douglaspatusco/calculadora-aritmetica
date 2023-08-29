<script setup>
    import Header from './components/Header.vue'
    import Main from './components/Main.vue'
    import Result from './components/Result.vue'
    import { operacao, estado} from './scripts/Scripts.vue'
</script>

<template>
    <Header />
    <Main :estado="estado" />
    <Result :estado="estado" :operacao="operacao()" />
</template>