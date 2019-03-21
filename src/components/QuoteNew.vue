<template>
    <div class="row">
        <form>
            <div class="
            col-xs-12
            col-sm-8
            col-sm-offset-2
            col-md-6
            col-md-offset-3
            form-group
            ">
                <label>Quote</label>
                <textarea rows="3" class="form-control" v-model="quote">
                </textarea>
        
            </div>
            <div class="
            col-xs-12
            col-sm-8
            col-sm-offset-2
            col-md-6
            col-md-offset-3
            form-group
            ">
                <button class="btn btn-primary" @click.prevent="createNewQuote">
                    Add New Quote
                </button>
        
            </div>

        </form>
    </div>
</template>

<script>
export default {
    data: function(){
        return{
            quote: ''
        }
        
    },
    methods: {
        createNewQuote(){
            this.$emit('quoteAdded', this.quote)
            this.quote= ''
        }
    }
}
</script>

<style scoped>

    
</style>