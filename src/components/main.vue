<template>
    <div id="main" class="row">
        <div class="top row">
             <div class="logo col-md-1">
            <p>B-MARKET</p>
            </div>
            <div class="menu col-md-2"></div>
            <div class="search col-md-8"></div>
            <div class="city col-md-1"></div>
        </div>
        <div class="content row">
            <div class="products col-lg-10 col-lg-offset-1 col-md-12">
                <app-products></app-products>
            </div>
        </div>
    </div>
</template>

<script>
    import products from '../components/products'
    export default {
        components: {
            'AppProducts': products
        },
        name: "main"
    }
</script>

<style scoped>
    #main {
        width: 100%;
        height: 100%;
    }
    .top {
        width: 100%;
        height: 50px;
        float: left;
    }
    .logo{
        height: 100%;
        float: left;
    }
    .menu{
        height: 100%;
        float: left;
        background-color: black;
    }
    .search{
        height: 100%;
        background-color: antiquewhite;
    }
    .city{
        height: 100%;
        background-color: blue;
    }
    .content {
        height: calc(100% - 50px);
    }
    .products {
        padding: 0;
        height: 100%;
    }
</style>
