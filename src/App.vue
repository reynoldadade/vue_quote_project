<template>
	<div class="container">
		<!-- this component aceepts quotes as props to display in a grid -->
		<app-header
			:quoteCount="quotes.length"
			:maxQuotes="maxQuotes"
		></app-header>
		<app-new-quote @quoteAdded="newQuote" />
		<app-quote-grid
			:quotes="quotes"
			@quoteDeleted="deleteQuote"
		></app-quote-grid>
		<div class="row">
			<div class="col text-center">
				<div class="alert alert-info" role="alert">
					Info: CLick on a quote to delete it
				</div>
			</div>
		</div>
	</div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
	name: 'App',
	components: {
		//uses all these components
		AppQuoteGrid: QuoteGrid,
		AppNewQuote: NewQuote,
		AppHeader: Header,
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
			if (this.quotes.length >= this.maxQuotes) {
				return alert('Please delete quotes first!');
			}
			this.quotes.push(quote);
		},
		//@vuese
		//this method delete quote by index
		// @arg index is the index of the quote to delete
		deleteQuote(index) {
			this.quotes.splice(index, 1);
		},
	},
};
</script>

<style></style>
