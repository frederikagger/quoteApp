<template>
    <div class="container">
        <Statusbar v-bind:number-of-quotes="Allquotes.length" v-bind:max-quotes="maxQuotes"></Statusbar>
        <AddQuote @quoteAdded="newQuote"></AddQuote>
        <AllQuotes @quoteDeleted="deleteQuote" v-bind:quotes="Allquotes"></AllQuotes>
    </div>
</template>

<script>
    import AllQuotes from "@/components/AllQuotes";
    import Status from "@/components/ProgressBar";
    import AddQuote from "@/components/AddQuote";

    export default {
        components: {
            'AllQuotes': AllQuotes,
            'Statusbar': Status,
            'AddQuote': AddQuote

        },
        data: function () {
            return {
                Allquotes: [],
                maxQuotes: 10
            }
        },
        methods: {
            newQuote(quote) {
                if (this.quotes.length<this.maxQuotes){
                    this.quotes.push(quote)
                }

            },
            deleteQuote(index){
                this.quotes.splice(index, 1);
            }
        }
    }
</script>

<style>

</style>
