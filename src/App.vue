<script setup>
    import { reactive } from 'vue';
    import Header from './components/Header.vue'
    import Main from './components/Main.vue'
    import Result from './components/Result.vue'

    const estado = reactive({
        numero1: '',
        numero2: '',
        operador: 'adicao',
        resultado: 0,
    })

    const adicao = () => { 
        const resultNumber = parseInt(estado.numero1) + parseInt(estado.numero2);
        return resultNumber
    }

    const subtracao = () => {
        const resultNumber = parseInt(estado.numero1) - parseInt(estado.numero2);
        return resultNumber
    }

    const multiplicacao = () => {
        const resultNumber = parseInt(estado.numero1) * parseInt(estado.numero2);
        return resultNumber
    }

    const divisao = () => {
        const resultNumber = parseInt(estado.numero1) / parseInt(estado.numero2);
        return resultNumber
}

    const operacao = () => {
        const { operador } = estado;

        switch(operador) {
            case 'adicao': {
            return adicao();
            }
            case 'subtracao': {
            return subtracao();
            }
            case 'multiplicacao': {
            return multiplicacao();
            }
            case 'divisao': {
            return divisao();
            }
        }
    }

    console.log(estado.resultado)
</script>

<template>
    <Header />
    <Main :estado="estado" />
    <Result :estado="estado" :operacao="operacao()" />
</template>