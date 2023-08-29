<script setup>
    import { reactive } from 'vue';

    const estado = reactive({
        numero1: 0,
        numero2: 0,
        operador: 'adicao',
        resultado: 0,
    })

const opAdicao = () => { return estado.numero1 + estado.numero2 }

const opSubtracao = () => { return estado.numero1 - estado.numero2 }

const opMultiplicacao = () => { return estado.numero1 * estado.numero2 }

const opDivisao = () => { return estado.numero1 / estado.numero2 }

const getOperacao = () => {
    const { operador } = estado;

    switch(operador) {
        case 'adicao': {
        return opAdicao();
        }
        case 'subtracao': {
        return opSubtracao();
        }
        case 'multiplicacao': {
        return opMultiplicacao();
        }
        case 'divisao': {
        return opDivisao();
        }
        default:
        return opAdicao();
    }
}

console.log(opAdicao(2, 4))
console.log(estado.numero1)
console.log(estado.numero2)
console.log(estado.resultado)
</script>

<template>
    <header class="p-5 mb-4 mt-4 bg-light text-center">
        <h1>Calculadora aritmética</h1>
        <p>Escolha dois números e a operação.</p>
    </header>
    <main class="container">
        <div class="row justify-content-center mx-5 inputs">
        <input :value="estado.numero1" @keyup="evento => estado.numero1 = evento.target.value" class="col-md-3 rounded-2 text-center form-control" type="number" placeholder="Número 1">
        <select @change="evento => estado.operador = evento.target.value" class="col-md-3 rounded-2 text-center form-control select" multiple>
            <option @click="estado.operador === 'adicao'" value="adicao">+</option>
            <option @click="estado.operador === 'subtracao'" value="subtracao">-</option>
            <option @click="estado.operador === 'multiplocacao'" value="multiplicacao">*</option>
            <option @click="estado.operador === 'divisao'" value="divisao">/</option>
        </select>
        <input :value="estado.numero2" @keyup="evento => estado.numero2 = evento.target.value" class="col-md-3 rounded-2 text-center form-control" type="number" placeholder="Número 2">
        </div>
    <p class="resultado text-center my-5">{{ estado.resultado }}</p>
    </main>

</template>

<style scoped>
.row {
    gap: 16px
}

.inputs input, select {
    width: 100px;
}

input[type="number"]::-webkit-outer-spin-button,
input[type="number"]::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
}

.select {
    overflow: hidden;
    -webkit-appearance: none;
    -moz-appearance: none;
    text-indent: 1px;
}
</style>
