<template>
    <div class="container">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label> Quote </label>
                <textarea class="form-control" rows="3" type="text" v-model="dataFirebase.text"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="submit"> Add Quote</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        name: "AddQuote",
        data: function () {
            return {
                dataFirebase: {
                    text: '',
                    name: 'kaj'
                }


            }
        },
        methods: {
            add() {
                this.$emit('quoteAdded', this.text);
                this.text = '';
            },
            submit() {
                this.$http.post('https://firstfirebase-2c5b6.firebaseio.com/data.json', this.dataFirebase)
                .then(response => {
                    console.log(response)
                });
            }
        }

    }
</script>

<style scoped>
    .col-sm-offset-2 {
        text-align: center;
    }

</style>