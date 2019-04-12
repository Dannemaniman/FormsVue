<template>
    <div class="row">
        <form>
             <div class="col-sm8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label>Quote</label>
                <textarea class="form-control" rows="3" v-model="quote"></textarea> <!-- sätt propertyn till v-model-->
             </div>
              <div class="col-sm8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button> <!-- prevent = skicka inte formen! (den kommer annars att uppdatera sidan) -->
             </div>                             <!-- Anropa metoden createNew-->
        </form>
    </div>
</template>

<script>
export default {
    data: function() {
        return {
            quote: ''
        }
    },
    methods: {
        createNew() {
            this.$emit('quoteAdded', this.quote); //Skicka tillbaka värden
            this.quote = '';
        }
    }
}
</script>

<style>
  
</style>

