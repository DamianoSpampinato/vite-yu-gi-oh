<script>
import Card from './Card.vue'
import {store} from '../store.js'
export default{
    name: 'CardsList',
    components: {
        Card
    },
    data(){
        return{
            store
        };
    }
}
</script>

<template>
    <main>
        <div class="container ms-bg-primary p-2 d-flex justify-content-center">
            <div class="container d-flex m-1 flex-wrap">
                <div class="row">
                    <Card v-for="card in store.cardsArray" :key="card.id" :cardInfo="card"></Card>
                </div>
            </div>
        </div>

    </main>
    
</template>


<style scoped lang="scss">
.ms-bg-primary{
    background-color: white;
    
}

</style>