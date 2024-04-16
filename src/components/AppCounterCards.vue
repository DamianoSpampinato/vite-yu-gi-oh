<script>
import { store } from './../store.js'
export default{
    name: 'AppCounterCards',
    data(){
        return {
            store
        }
    },
    computed: {
        cardsLength() {
            return store.cardsArray.length;
        }
    }
}

</script>
<template>
<div>
    <small>Numero di Carte trovate: <span>{{ cardsLength }}</span></small>
</div>
</template>
<style scoped lang="scss">
small{
    position: fixed;
    bottom:0;
    left:0;
    height: 70px;
    line-height: 70px;
    background-color: orange;
}
</style>