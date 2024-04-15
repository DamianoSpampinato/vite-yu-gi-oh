<script>
export default{
    name: 'Card',
    props:{
        cardInfo: Object
    }
}
</script>

<template>
<div class="col-3">
    <div class="card">
        <img :src="cardInfo.card_images[0].image_url_small" class="card-img-top" alt="...">
        <div class="card-body ms-card-body">
            <h5 class="card-title">{{ cardInfo.name }}</h5>
            <p class="card-text">{{ cardInfo.archetype }}</p>
        </div>  
    </div>
</div>

    
</template>


<style scoped lang="scss">
.ms-card-body{
        background-color: orangered;
    }
    .card{
       height: 100%;
      
    }
</style>