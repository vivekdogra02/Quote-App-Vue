<template>
<div>
  <div class="row">
      <div class="col-sm-12">
          <h3>Quote Added</h3>
      <div class="progress">
          <div class="progress-bar" role="progressbar" 
          aria-valuemin="0"
          aria-valuenow="40"
          aria-valuemax="100"
          :style="{width: (quoteCount/maxQuote) * 100 + '%'}">
        {{quoteCount}} / {{maxQuote}}
          </div>
      </div>
      </div>

  </div>
  <div class="row" v-if="quoteCount >= maxQuote">
        <div class="col-sm-12 text-center">
          <div class="alert alert-danger">
            You can't add more than {{maxQuote}} Quotes.
            Please Delete and then add.
          </div>
        </div>
</div>
</div>
  
</template>
<script>
export default {
  props: ['quoteCount', 'maxQuote']
}
</script>

<style scoped>

</style>

