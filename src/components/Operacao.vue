<script setup>
    const props = defineProps(['operacao', 'resultado'])
</script>

<template>
    <div class="d-flex justify-content-center flex-column align-items-center">
        <div class="col-md-3">
            <select class="form-control" @change="props.operacao">
                <option value="soma">Soma</option>
                <option value="subtracao">Subtração</option>
                <option value="multiplicacao">Multiplicação</option>
                <option value="divisao">Divisão</option>
            </select>
            <p class="text-center mt-4 mb-4">O resultado da Operação é:</p>
            <h2 class="d-flex justify-content-center align-items-center mb-4">{{props.resultado}}</h2>
        </div>
    </div>
</template>