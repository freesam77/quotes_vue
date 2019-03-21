<template>
    <div class="container">
            <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
            <app-quote-new @quoteAdded="addNewQuote"></app-quote-new>
            <app-quote-grid :quotes="quotes" @quoteDeleted="removeQuote"></app-quote-grid>
            <div class="row">
                <div class="col-sm-12">
                    <div class="alert alert-info">
                        Clicking each quote will delete them.
                    </div>
                </div>
            </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue';
    import QuoteGrid from './components/QuoteGrid.vue';
    import QuoteNew from './components/QuoteNew.vue';
    export default {
        data: function(){
            return{
                maxQuotes:4,
                quotes:[
                    "You cooled off yet kid?",
                    "Do your homework first!",
                    "Adios kid!"
                ]
            }
        },
        components:{
            appHeader: Header,
            appQuoteGrid: QuoteGrid,
            appQuoteNew: QuoteNew
        },
        methods:{
            addNewQuote(quote){
                if(this.quotes.length >= this.maxQuotes){
                    return alert("You have reached the maximum number of Quotes, please delete some first!")
                }
                this.quotes.push(quote)
            },
            removeQuote(index){
                this.quotes.splice(index,1)
            }
        }
    }
</script>

<style>
</style>
