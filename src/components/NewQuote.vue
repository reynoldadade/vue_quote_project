<template>
	<div class="row">
		<!-- this form is used to input new quotes -->
		<div class="col-sm-8 offset-sm-2 col-md-6 offset-md-3 col-12">
			<form>
				<div class="form-group">
					<label>Quote</label>
					<textarea
						class="form-control"
						rows="3"
						v-model="quote"
					></textarea>
				</div>
				<div
					class="col-sm-8 offset-sm-2 col-md-6 offset-md-3 col-12 form-group"
				>
					<button class="btn btn-primary" @click.prevent="createNew">
						Add Quote
					</button>
				</div>
			</form>
		</div>
	</div>
</template>

<script>
export default {
	data: function() {
		return {
			quote: '',
		};
	},
	methods: {
		//@vuese
		//this method will be used to emit a new quote to the QuoteGrid
		createNew() {
			// this event emits the newest quote
			this.$emit('quoteAdded', this.quote);
			this.quote = '';
		},
	},
};
</script>

<style></style>
