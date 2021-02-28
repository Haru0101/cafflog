<template>
    <div class="wrapper">
        <section>
            <EditDisplay v-if="isEditDisplay"></EditDisplay>
            <DrinkList :drinks="drinks" v-else></DrinkList>
        </section>
        <pre>
            {{ $data }}
        </pre>
        <footer>
            <button type="button" @click="toggleEditDisplay()">
                <span v-if="isEditDisplay">リスト表示</span>
                <span v-else>追加画面表示</span>
            </button>
        </footer>
    </div>
</template>
<script>
    import EditDisplay from "./components/EditDisplay";
    import DrinkList from "./components/DrinkList";
    export default {
        components: {
            DrinkList,
            EditDisplay
        },
        data() {
            return {
                isEditDisplay: false,
                drinks: [],
                totalCaffine: 0
            }
        },
        methods: {
            toggleEditDisplay(){
                this.isEditDisplay = !this.isEditDisplay;
            }
        }
    }

</script>
<style lang="scss" scoped>
.wrapper {padding: 10px 15px;}
</style>