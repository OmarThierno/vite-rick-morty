<script>
    import {store} from '../store'
    export default {
        data() {
            return {
                store,
                status: ['All', 'Alive', 'Dead', 'Unknown']
            }
        }
    }
</script>

<template>
    
    <div class="d-flex justify-content-between">
        <select @change="$emit('filterSeep')" v-model="store.status">
            <!-- <option selected>Open this select menu</option> -->
            <option v-for="curStatus in status" :value="curStatus">{{ curStatus }}</option>
        </select>
        <div>
            <p>character {{ store.dataArray.length }}</p>
        </div>
    </div>
    
</template>

<style lang="scss" scoped>

</style>