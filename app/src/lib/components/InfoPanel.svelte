<script lang="ts">
	export let output : number;
</script>

<section class="info-panel">
	<p class="info-panel__title">
		ответ:
	</p>
	<p class="info-panel__subtitle font--lg">
		{output}
	</p>
</section>

<style lang="scss">
	.info-panel {
		min-width: 30vw;
		display: flex;
		flex-direction: column;
		background-color: var(--color-dark);
		padding: var(--spacing-sm) var(--spacing-md);
		border-radius: var(--border-radius-lg);
		gap: var(--spacing-xs);

		&__title {
			color: var(--color-orange);
		}

		&__subtitle {
			color: var(--color-light);
			text-align: center;
		}
	}
</style>
