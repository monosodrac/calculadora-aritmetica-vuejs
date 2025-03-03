<script setup>
const props = defineProps(['valorUm', 'valorDois', 'trocaOperador']);
</script>

<template>
    <form class="d-flex justify-content-center align-items-center mb-2">
        <input placeholder="0" @keyup="props.valorUm" type="number" />
        <select @change="props.trocaOperador" class="form-control ms-3 me-3 text-center">
            <option selected value="somar">+</option>
            <option value="sub">-</option>
            <option value="mult">x</option>
            <option value="divid">/</option>
        </select>
        <input placeholder="0" @keyup="props.valorDois" type="number" />
    </form>
</template>

<style scoped>
.form-control {
    width: 20%;
}

input {
    border: 1px solid #fff;
    border-radius: 10px;
    width: 20%;
    height: 2.5rem;
    background-color: transparent;
    color: #fff;
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

@media (max-width: 767px) {
    form {
        flex-direction: column;
    }

input {
    width: 50%;
}

    select {
        margin: 1rem 0;
    }
}
</style>