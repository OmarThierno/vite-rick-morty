<script>
export default {
    props: {
        cardObj: Object,
    },
    data() {
        return {

        }
    }
}
</script>

<template>
    <div class="">
        <img :src="cardObj.image" class="img-fluid rounded-circle mb-3" alt="">
        <h6>{{ cardObj.name }}</h6>

        <div class="fs-6 fst-italic">{{ cardObj.status }}</div>
        <div class="fw-light">{{ cardObj.species }}</div>
    </div>
   
</template>

<style lang="scss" scoped>

</style>

