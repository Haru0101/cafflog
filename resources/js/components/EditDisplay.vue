<template>
    <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model="newDrink.name">
        <label for="quantity">カフェイン量</label>
        <input type="number" id="quantity" v-model="newDrink.quantity">mg/100mL
        <button type="button" @click="addDrink()">Add</button>
    </div>
</template>
<script>
export default {
    data(){
        return {
            newDrink: {
                name:"",
                quantity: ""
            }
        }
    },
    methods:{
        addDrink() {
            console.log('addDrink');
            let newDrink = {
                name: this.newDrink.name,
                quantity: this.newDrink.quantity
            };
            this.$parent.drinks.push(newDrink);
            this.newDrink.name = "";
            this.newDrink.quantity = "";
        }
    }
}
</script>
<style lang="scss" scoped>
label {display: block;}
button {display: block;margin-top: 40px;height: 80px;width: 100%;font-size: 16px;}
</style>