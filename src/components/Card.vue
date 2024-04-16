<script>
export default{
    name: 'Card',
    props:{
        cardInfo: Object
    }
}
</script>

<template>
<div class="col-xl-2  col d-flex justify-content-center">
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
        background-color: rgba(255,127,80,0.7);
    }
    .card{
        width: 150px;
        height: 100%;
        background: none;
        transition: all 300ms ease-in-out;
      
    }
    .card:hover  {
        width: 200px;
        height: 100%;
    }
</style>