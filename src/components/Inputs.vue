<script setup>
    const props = defineProps(['firstNumber', 'secondNumber', 'operation'])
</script>
<template>
    <input @keyup="props.firstNumber" @change="props.firstNumber" type="number" class="form-control text-center fw-medium fs-5" placeholder="1° value">
    <select @change="props.operation" class="form-control my-2 w-25 text-center fw-bolder">
        <option value="sum">+</option>
        <option value="sub">-</option>
        <option value="mul">x</option>
        <option value="div">/</option>
    </select>
    <input @keyup="props.secondNumber" @change="props.secondNumber" type="number" class="form-control text-center fw-medium fs-5" placeholder="2° value">
</template>