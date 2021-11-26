<template>
    <div class="product">
        <img :src="details.poster" :alt="details.title">
        <h2>{{details.title.toUpperCase()}}</h2>
        <span>{{details.author}}</span><br>
        <span>{{details.year}}</span>

    </div>
</template>

<script>
export default {
    name: 'Maincards',
    props: {
        details: Object,
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    .product{ 
        background-color:rgba(46,58,70,255);
        width: 15%; 
        padding:10px;
        margin: 50px 10px 5px 0px;
        text-align: center;
        img{
            width:100%;
            height:150px;
        }
        h2{
            font-size: 15px;
        }
        span{
            color:grey;
            font-size: 15px;
        }
        
    }
</style>