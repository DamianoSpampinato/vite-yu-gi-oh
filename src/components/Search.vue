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
<select @change="$emit('searchPerformed')" v-model="store.searchedArchetype">
    <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
</select>
</template>
<style scoped lang="scss"></style>