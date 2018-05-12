<template>
    <div  class="container">
      <app-header :quoteCount="quotes.length" :maxQuote="maxQuotes"></app-header>
      <new-quote @quoteAdded="newQuote"></new-quote>
      <quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></quote-grid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">
            Click on the Quote to delete it.
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid';
import NewQuote from './components/NewQuote';
import Header from './components/Header';
export default {
  data: function() {
    return {
      quotes: ['Just to see'],
      maxQuotes: 10
    }
  },
  methods: {
    newQuote(quote) {
      if(this.quotes.length >= this.maxQuotes) {
        return 
      }
      this.quotes.unshift(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index,1); 
    }
  },
  components: {
    quoteGrid: QuoteGrid,
    newQuote: NewQuote,
    appHeader: Header
  }
}
</script>


<style lang="scss">
</style>
