<script>
import { store } from './../store.js'
export default{
    name: 'Search',
    data(){
        return {
            store
        }
    },
    methods:{
        consoleLog(){

            console.log(store.searchedArchetype)
        }
    }
}

</script>
<template>
    <div class="container">

        <select aria-placeholder="filtra per archetipi" @change="$emit('searchPerformed')" v-model="store.searchedArchetype">
            <option value="">Tutti</option>
            <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
        </select>
    </div>
</template>
<style scoped lang="scss">
select{
    background-color: orange;
    margin-bottom: 10px;
    padding: 5px;
    width:50%;
}
</style>