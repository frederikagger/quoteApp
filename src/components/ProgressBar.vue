<template>
    <div class="container">
        <h1> Quotes added </h1>
        <div id="outerbar">
            <div id="innerbar" v-bind:style="{width: numberOfQuotes/maxQuotes*100+'%'}">
                <p>{{numberOfQuotes}}/{{maxQuotes}} </p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Status",
        props: ['numberOfQuotes', 'maxQuotes']
    }
</script>

<style scoped>
    #outerbar {
        border: 1px solid;
        width: 100%;
        height: 38px;
    }

    #innerbar {
        background-color: darkcyan;
        height: 100%;

    }

    p {
        text-align: center;
        color: white;
        font-family: Cambria;
        font-size: 22px;
    }

</style>