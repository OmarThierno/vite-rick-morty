<script>
import {store} from './store'
import axios from 'axios'
import AppMain from './components/AppMain.vue'
import AppSeach from './components/AppSeach.vue'
export default {
    components: {
        AppMain,
        AppSeach,
    },
    data() {
        return {
            store,
        }
    },
    created() {
        axios.get('https://rickandmortyapi.com/api/character').then((resp) => {
            // console.log(resp.data.results);
            this.store.dataArray = resp.data.results;
        })
    },
    methods: {
        getCharacter() {
            const params = {
                status: '',
            }
            if(this.store.status !== 'All') {
                params.status = this.store.status;
            }

            axios.get('https://rickandmortyapi.com/api/character',{
                params,
            }).then((resp) => {
                this.store.dataArray = resp.data.results;
            })
        }
    }
}
</script>

<template>
    <div class="container text-center py-3">
        <h1>Rick and Morty</h1>

        <AppSeach @filterSeep="getCharacter" />

        <AppMain :cardArray="store.dataArray"/>
    </div>

</template>

<style lang="scss">
    body {
        background:repeating-linear-gradient(90deg, rgba(64, 64, 64, 0.52) 5%, rgba(221, 221, 221, 0.49) 10%),repeating-linear-gradient(-180deg, rgba(64, 64, 64, 0.52) 5%, rgba(221, 221, 221, 0.49) 10%)
    }
</style>
