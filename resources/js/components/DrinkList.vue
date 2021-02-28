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
<style lang="scss" scoped>
li {list-style: none;width: 100%;height: 100px;display: block;margin: 0;padding: 0;}
button {width: 100%;height: 100%;}
</style>