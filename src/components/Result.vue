<script setup>
    const props = defineProps(['operationSelected'])
</script>
<template>
    <span class="fs-4 fw-bolder">=</span>
    <span id="result" class="fs-4 fw-bolder">{{ props.operationSelected }}</span>
</template>