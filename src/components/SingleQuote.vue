<template>
      <div class="col-md-3 quote">
          <div @click="quoteAlert(quote)" class="inner-quote">{{ quote }}</div>
      </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  props: ['quote'],
  methods: {
      quoteAlert(quote) {
          eventBus.$emit('selectedQuote', quote);
      }
  }
}
</script>

<style>

</style>
