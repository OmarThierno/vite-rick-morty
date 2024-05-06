<script>
import AppCard from "./AppCard.vue";
export default {
    components: {
        AppCard,
    },
    props: {
        cardArray: Array,
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-4 row-cols-lg-5">
        <div v-for="curObj in cardArray" class="col g-3">
            <AppCard :cardObj="curObj"/>
        </div>
    </div>
   
</template>

<style lang="scss" scoped>

</style>
