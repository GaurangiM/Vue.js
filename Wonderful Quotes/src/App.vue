<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxCount="maxQuotes"></app-header>
        <app-new-quote @NewQuoteAdded="newQuote"></app-new-quote>
        <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
        <div class="row ">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info ">Info: Click on a Quote to delete it !</div>
            </div>
            
        </div>
    </div>
</template>

<script>
    import Header from './components/Header.vue'
    import NewQuote from './components/NewQuote.vue'
    import QuoteGrid from './components/QuoteGrid.vue'
    export default {
        data: function() {
            return {
                quotes: [
                    'My 1st quote',
                    'My 2nd quote',
                    'My 3rd quote',
                    'My 4th quote',
                    'My 5th quote',
                    'My 6th quote'
                ],
                maxQuotes: 10
            }
        },
        components: {
            appQuoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        },
        methods: {
            newQuote(quote) {
                if(this.quotes.length >= this.maxQuotes)
                    return alert("Please delete Quotes first !");
                this.quotes.push(quote);
            },
            deleteQuote(index) {
                this.quotes.splice(index,1);
            }
        }
        
    }
</script>

<style>
</style>
