<template>
	<div class="row">
		<app-quote
			v-for="(quote, index) in quotes"
			:key="quote"
			@click.native="deleteQuote(index)"
			>{{ quote }}</app-quote
		>
	</div>
</template>

<script>
import Quote from './Quote.vue';
export default {
	props: {
		// this quotes prop is a list of quotes to display
		quotes: {
			type: Array,
			required: true,
		},
	},
	components: {
		appQuote: Quote,
	},
	methods: {
		// @vuese
		//this method is used to emit the index of the quote to delete
		// @arg index:  This argument represents the index of the item to delete the array
		deleteQuote(index) {
			//this event will emit the index of the array to delete
			//@arg is the index of the array being deleted
			this.$emit('quoteDeleted', index);
		},
	},
};
</script>

<style></style>
