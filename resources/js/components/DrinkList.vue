<template>
    <ul>
        <li v-for="(drink, index) in drinks" :key="index">
            <button @click="countTotalCaffineQuantity(drink.quantity)">
                {{drink.name}}（{{ drink.quantity }}mg/100mL）
            </button>
        </li>
    </ul>
</template>
<script>
export default {
    props:['drinks'],
    methods: {
        countTotalCaffineQuantity(caffineQuantity){
            this.$parent.totalCaffine += Number(caffineQuantity);
        }
    }
}
</script>