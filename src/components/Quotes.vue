<template>
  <div style="margin-top: 40px;" class="row">
      <single-quote  v-for="quote in quoteArray" :quote="quote"></single-quote>
  </div>
</template>

<script>
import SingleQuote from './SingleQuote.vue';
import { eventBus } from '../main.js';

export default {
  props: ['progress'],
  data: function() {
      return {
        quoteArray: []
      };
  },
  components: {
    singleQuote: SingleQuote
  },
  created() {
      eventBus.$on('newQuote', (quote) => {
        this.quoteArray.push(quote);
      });
      eventBus.$on('selectedQuote', (quote) => {
        var index = this.quoteArray.indexOf(quote);
        this.quoteArray.splice(index, 1);
        this.progress.value -= 10;
      });
  }
}
</script>

<style>

</style>
