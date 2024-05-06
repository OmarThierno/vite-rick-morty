<script>
import axios from 'axios'
import AppMain from './components/AppMain.vue'
export default {
    components: {
        AppMain,
    },
    data() {
        return {
            dataArray: [],
        }
    },
    created() {
        axios.get('https://rickandmortyapi.com/api/character').then((resp) => {
            console.log(resp.data.results);
            this.dataArray = resp.data.results;
        })
    }
}
</script>

<template>
    <div class="container text-center py-3">
        <h1>Rick and Morty</h1>
        <AppMain :cardArray="dataArray"/>
    </div>

</template>

<style lang="scss">

</style>
