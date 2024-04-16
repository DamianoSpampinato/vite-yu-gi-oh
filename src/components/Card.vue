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
            <div class="card-title">{{ cardInfo.name }}</div>
            <div class="card-text">{{ cardInfo.archetype }}</div>
        </div>  
    </div>
</div>

    
</template>


<style scoped lang="scss">
.ms-card-body{
        background-color: orangered;
    }
    .card{
        width: 150px;
        height: 100%;
      
    }
</style>