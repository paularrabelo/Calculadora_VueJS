<script setup>
    const props = defineProps(['num1', 'num2'])
</script>

<template>
    <form >
        <div class="d-flex justify-content-center flex-column align-items-center">
            <div class="col-3">
                <input @keyup="props.num1" class="form-control mb-4" type="number" placeholder="Digite um número">
                <input @keyup="props.num2" class="form-control mb-4" type="number" placeholder="Digite outro número">
            </div>
        </div>
    </form>
</template>