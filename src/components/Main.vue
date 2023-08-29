<script setup>
    const props = defineProps(['estado'])
</script>

<template>
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
