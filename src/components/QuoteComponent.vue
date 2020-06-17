<template>
    <div class="col-md-2">
        <p> {{quote}}  </p>
    </div>
</template>

<script>
    export default {
        props: ['quote']
    }
</script>

<style scoped>
    div {
        border: solid 1px;
        width: 250px;
        height: 100px;
        box-shadow: 1px 1px 2px black;
        padding: 10px;
    }

    p {
        text-align: center;
        font-family: "Comic Sans MS";
    }
    div:hover{
        background-color: bisque;
    }


</style>
