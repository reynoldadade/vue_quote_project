<template>
  <div class="row">
      <app-quote v-for="quote in quotes" :key="quote">{{quote}}</app-quote>
  </div>
</template>

<script>
import Quote from './Quote.vue'
export default {
    props: {
        // this quotes prop is a list of quotes to display
        quotes: {
            type: Array,
            required: true
        }
    },
    components: {
        appQuote: Quote
    }
}
</script>

<style>

</style>