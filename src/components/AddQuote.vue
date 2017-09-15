<template>
  <div class="row">
      <div class="col-md-6 col-md-offset-3">
          <p style="font-weight: bold">Quote</p>
          <textarea id="textArea" v-model="quote" class="form-control" rows="5"></textarea>
          <button @click="addQuote" style="margin-top: 20px" class="btn btn-primary center-block">Add Quote</button>
      </div>
  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  data: function() {
    return {
      quote: ''
    }
  },
  props: ['progress'],
  methods: {
    addQuote() {
      if(this.progress.value < 100 && this.quote !== ''){
        this.progress.value += 10;
        eventBus.$emit('newQuote', this.quote);
      } else if (this.quote === '') {
        alert("Please write your quote");
      } else {
        alert("You have reached the maximum number of Quotes!");
      }
      document.getElementById("textArea").value = '';
    }
  }
}
</script>

<style>

</style>
