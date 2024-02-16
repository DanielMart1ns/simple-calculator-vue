<script setup>
    import { reactive } from 'vue';
    import Header from './components/Header.vue'
    import Inputs from './components/Inputs.vue'
    import Result from './components/Result.vue'

    const status = reactive({
        firstValue: '',
        secondValue: '',
        filter: 'sum'
    })

    const getFirstValue = (data) => {
        status.firstValue = parseInt(data.target.value)
    }

    const getSecondValue = (data) => {
        status.secondValue = parseInt(data.target.value)
    }

    const getOperation = (operation) => {
        status.filter = operation.target.value
    }

    function operationSelected () {
        const {filter} = status
        const {firstValue} = status
        const {secondValue} = status

        switch(filter){
            case 'sum':
                return firstValue + secondValue;

            case 'sub':
                return firstValue - secondValue;
            
            case 'mul':
                return firstValue * secondValue;

            case 'div':
                return firstValue / secondValue;
        }
    }
</script>

<template>
    <div class="container p-4">
        <Header></Header>
        <div class="col-md-3 m-auto d-flex flex-column align-items-center">
            <Inputs :first-number="getFirstValue" :second-number="getSecondValue" :operation="getOperation"></Inputs>
            <Result :operation-selected="operationSelected()"></Result>
        </div>
    </div>
</template>

<style scoped>
</style>