<template>
    <div id="products" class="row">
        <div class="catalog col" :class="catalogColMdClass">
            <div class="item col" v-for="i in 10" :class="itemColMdClass">
                <div class="item-content"></div>
            </div>
        </div>
        <div class="info col" :class="infoColMdClass">
            <div class="left-info col col-md-5">
                <div class="images"></div>
                <div class="options"></div>
            </div>
            <div class="right-info col col-md-7">
                <div class="store"></div>
                <div class="map"></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "products",
        data () {
            return {
                compact: true
            }
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
    .catalog {
        height: 100%;
        background-color: red;
    }
    .item {
        background-color: green;
        /*padding: 20px;*/
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
</style>
