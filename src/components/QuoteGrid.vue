<template>
    <div class="row">
        <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)"> {{ quote }} </app-quote> <!--what .native does is tells vuejs even if i clicked on the html code, treat is as if I've clicked on the <app-quote> -->
    </div>
</template>

<script>
import Quote from './Quote.vue'

export default { //Se detta som en class!!! med variabler och metoder:
    props: ['quotes'],  //props = Properties set from outside.
    components: {
        appQuote: Quote
    },
    methods: {
        deleteQuote(index) {
            this.$emit('quoteDeleted', index)
        }
    }
}
</script>

<style>
  
</style>

