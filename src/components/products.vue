<template>
    <div id="products" class="row">
        <div class="catalog-wrapper col" :class="catalogColMdClass">
            <div class="catalog">
                <div class="item col" v-for="i in 50" :class="itemColMdClass">
                    <div class="item-content"></div>
                </div>
            </div>
        </div>
        <div class="info col" v-if="compact" :class="infoColMdClass">
            <div class="left-info col col-md-5">
                <div class="images"></div>
                <div class="options"></div>
            </div>
            <div class="right-info col col-md-7">
                <div class="store"></div>
                <div class="map">
                    <div id="map">

                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "products",
        data () {
            return {
                compact: true,
                products: []
            }
        },
        methods: {
            initMap() {
                this.map = new google.maps.Map(document.getElementById('map'), {
                  center: {lat: -34.397, lng: 150.644},
                  zoom: 8
                });
            }
        },
        mounted () {
            if (this.compact) {
                this.initMap();
            }
            this.axios.get('http://localhost:8000/products/').then((response) => {
                console.log(response.data)
            }).catch((error) => {
                console.log(error)
            });
        },
        computed: {
            catalogColMdClass () {
                return {
                    'col-md-3': this.compact,
                    'col-md-12': !this.compact
                }
            },
            itemColMdClass () {
                return {
                    'col-md-12': this.compact,
                    'col-md-3': !this.compact
                }
            },
            infoColMdClass () {
                return {
                    'col-md-9': this.compact,
                    'col-md-0': !this.compact
                }
            }
        }
    }
</script>

<style scoped>
    #products {
        height: 100%;
        background-color: blue;
    }
    .catalog-wrapper {
        height: 100%;
        background-color: red;
        padding: 10px;
    }
    .catalog {
        width: 100%;
        height: 100%;
        overflow-y: auto;
    }
    .item {
        position: relative;
        background-color: green;
    }
    .item:before {
        content: "";
        display: block;
        padding-top: 35%;
    }
    .item-content {
        position: absolute;
        top: 20px;
        left: 20px;
        right: 20px;
        bottom: 20px;
        background-color: aqua;
    }
    .info {
        height: 100%;
        background-color: darkcyan;
    }
    .left-info, .right-info{
        height: 100%;
        display: flex;
        flex-flow: column;
    }
    .left-info {
        background-color: brown;
        padding: 20px;
    }
    .right-info {
        background-color: fuchsia;
        padding: 20px;
    }
    .images {
        width: 100%;
        padding-top: 75%;
        background-color: blueviolet;
        float: left;
    }
    .options {
        width: 100%;
        margin-top: 20px;
        flex-grow: 1;
        background-color: aquamarine;
        float: left;
    }
    .store {
        width: 100%;
        padding-top: 30%;
        background-color: darkcyan;
        float: left;
    }
    .map {
        width: 100%;
        margin-top: 20px;
        flex-grow: 1;
        background-color: aliceblue;
        float: left;
        position: relative;
    }
    #map {
        position: absolute !important;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: red;
        z-index: 9;
    }
</style>
