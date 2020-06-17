<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)" v-bind:key="index" v-bind:quote="quote">
        </app-quote>
    </div>

</template>

<script>
    import QuoteComponent from "@/components/QuoteComponent";

    export default {
        name: "AllQuotes",
        props: {
            quotes: Array
        },
        components: {
            appQuote: QuoteComponent
        },
        methods: {
            deleteQuote(index) {
                this.$emit('quoteDeleted', index);
            }
        }
    }
</script>

<style scoped>
    list {
        border: yellow 1px;
        background-color: yellow;
    }

</style>