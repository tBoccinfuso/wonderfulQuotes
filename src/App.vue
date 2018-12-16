<template>
    <div class="container">
        <app-header :quoteCount="quoteCounter()" :maxQuotes="maxQuotes"></app-header>
        <new-quote @quoteAdded="theNewQuote"></new-quote>
        <!-- pass quotes array as data -->
        <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click a Quote to delete it.</div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';
    export default {
        data : function () {
            return {
                quotes: ['Test quote', 'Tom is kool.'],
                maxQuotes: 10
            }
        },
        components: {
            quoteGrid: QuoteGrid,
            newQuote: NewQuote,
            appHeader: Header
        },
        methods: {
            theNewQuote(quote) {
                // only add quote when less than maxQuote limit
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please remove quotes first')
                }
                this.quotes.push(quote)
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1);
            },
            quoteCounter() {
                return this.quotes.length;
            }
        }
    }
    
</script>

<style scoped>
    .alert{
        margin-top: 20px;
    }
</style>
