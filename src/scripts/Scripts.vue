<script>
    import { reactive } from 'vue';

    export const estado = reactive({
        numero1: '',
        numero2: '',
        operador: 'adicao',
        resultado: '',
    })

    export const adicao = () => { 
        const resultNumber = parseInt(estado.numero1) + parseInt(estado.numero2);
        return resultNumber
    }

    export const subtracao = () => {
        const resultNumber = parseInt(estado.numero1) - parseInt(estado.numero2);
        return resultNumber
    }

    export const multiplicacao = () => {
        const resultNumber = parseInt(estado.numero1) * parseInt(estado.numero2);
        return resultNumber
    }

    export const divisao = () => {
        const resultNumber = parseInt(estado.numero1) / parseInt(estado.numero2);
        return resultNumber
}

    export const operacao = () => {
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

</script>