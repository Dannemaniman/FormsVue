<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
        <quoteGrid :quotes="quotes" @quoteDeleted="deleteQuote">  <!-- binda min props(property set from outside) quotes till detta!!! -->
        </quoteGrid>
        <app-new-quote @quoteAdded="newQuote"></app-new-quote> <!--@ eller v-on lyssnar efte event -->
        <div class="">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">Info: Click on a Quote to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue'
    import NewQuote from './components/NewQuote.vue'
    import Header from './components/Header.vue'

    export default {
        data: function() {
            return {
                quotes: ['Just a Quote to see something'],
                maxQuotes: 10
            }
        },
        components: {
            quoteGrid: QuoteGrid,
            appNewQuote: NewQuote,
            appHeader: Header
        },
        methods: {
            newQuote(newQuote) {
                if (this.quotes.length >= this.maxQuotes) {
                    return alert('Please delete a quote first!')
                } 
                this.quotes.push(newQuote)
            },
            deleteQuote(index) {
                this.quotes.splice(index, 1); //Börjar ta bort vid index, och gör endast 1 element
            }
        }
    }
</script>

<style>
</style>
