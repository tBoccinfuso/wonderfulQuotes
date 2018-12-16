<template>
  <div class="row">
    <form action="">
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 form-group">
        <label for="quoteBox">Quote</label>
        <!-- v-model will bind the text to our quote data -->
        <textarea v-model="quote" class="form-control" name="quoteBox" id="quoteBox" cols="30" rows="3"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 form-group">
        <!-- @click.prevent stops the page from submitting -->
        <button class="btn btn-promary" @click.prevent="createNewQuote">Add Quote</button>
      </div>
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
       createNewQuote() {
         // send data and clear the textarea after
         this.$emit('quoteAdded', this.quote);
         this.quote = '';
       }
     }
   }
</script>
  
<style scoped>
  
</style>