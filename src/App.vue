<template>
	<div class="container">
		<!-- this component aceepts quotes as props to display in a grid -->
		<app-new-quote @quoteAdded="newQuote" />
		<app-quote-grid :quotes="quotes"></app-quote-grid>
		<div class="row">
			<div class="col text-center">
				<div class="alert info">
					Info: CLick on a quote to delete it
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';

export default {
	name: 'App',
	components: {
		AppQuoteGrid: QuoteGrid,
		AppNewQuote: NewQuote,
	},
	data: function() {
		return {
			quotes: ['Just a Quote to see something'],
			maxQuotes: 10,
		};
	},
	methods: {
		// @vuese
		// this method pushes a new quote to the quotes array, it catches the event sent by the newQuote Component
		newQuote(quote) {
			this.quotes.push(quote);
		},
	},
};
</script>

<style></style>
