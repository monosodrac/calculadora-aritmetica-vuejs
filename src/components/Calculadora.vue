<script setup>
const props = defineProps(['valorUm', 'valorDois', 'trocaOperador']);
</script>

<template>
    <form class="d-flex justify-content-center align-items-center mb-2">
        <input placeholder="Primeiro Valor" @keyup="props.valorUm" type="number" />
        <select @change="props.trocaOperador" class="form-control ms-2 me-2 text-center">
            <option selected value="somar">+</option>
            <option value="sub">-</option>
            <option value="mult">x</option>
            <option value="divid">/</option>
        </select>
        <input placeholder="Segundo Valor" @keyup="props.valorDois" type="number" />
    </form>
</template>

<style scoped>
.form-control {
    width: 20%;
}

select {
    background-color: transparent;
}

select:focus {
    box-shadow: none;
    background-color: transparent;
}

input[type=number]::-webkit-inner-spin-button,
input[type=number]::-webkit-outer-spin-button {
    -webkit-appearance: none;
    margin: 0;
}
</style>