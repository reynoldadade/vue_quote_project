<template>
	<div class="row">
		<h3>Quotes Added</h3>
		<div class="col-12">
			<div class="progress">
				<div
					class="progress-bar"
					role="progressbar"
					aria-valuenow="60"
					aria-valuemin="0"
					aria-valuemax="100"
					:style="{ width: (quoteCount / maxQuotes) * 100 + '%' }"
				>
					{{ quoteCount }} / {{ maxQuotes }}
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props: {
		quoteCount: {
			// number of quotes in the quote array
			type: Number,
			required: true,
		},
		maxQuotes: {
			//maximum number of quotes allowed to exist in an array
			type: Number,
			required: true,
		},
	},
};
</script>

<style></style>
