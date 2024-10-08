<script lang="ts">
	export let output : number;

	let leftInput : number;
	let rightInput : number;

	let selectOptions = [
		{id: 1, value: '+'},
		{id: 2, value: '-'},
		{id: 3, value: '*'},
		{id: 4, value: '/'},
	];
	let selectedOptionId = 0;

	const handleSubmit = () => {
		const selectedOptionValue = selectOptions[selectedOptionId - 1].value;

		switch (selectedOptionValue) {
			case '+':
				output = leftInput + rightInput;
				break;
			case '-':
				output = leftInput - rightInput;
				break;
			case '*':
				output = leftInput * rightInput;
				break;
			case '/':
				output = leftInput / rightInput;
				break;
			default:
				break;
		}
	};
</script>

<section class="control-panel">
	<form class="control-panel__form font--lg">
		<input class="control-panel__input" type="number" bind:value={leftInput} placeholder="">
		<select class="control-panel__select" bind:value={selectedOptionId}>
			{#each selectOptions as option}
				<option class="control-panel__option" value={option.id}>{option.value}</option>
			{/each}
		</select>
		<input class="control-panel__input" type="number" bind:value={rightInput}>
	</form>
	<button class="control-panel__btn btn" on:click={handleSubmit}>вычислить!</button>
</section>

<style lang="scss">
	.control-panel {
		display: flex;
		align-items: center;
		flex-direction: column;
		gap: var(--spacing-md);

		&__form {
			display: flex;
			gap: var(--spacing-xl);
		}

		&__input, &__select, &__option {
			text-align: center;
			padding: var(--spacing-xs) var(--spacing-sm);
			background-color: var(--color-dark);
			color: var(--color-light);
			border: 1px solid var(--color-dark);
			border-radius: var(--border-radius-md);
			outline: none;
			transition: var(--transition);

			&:focus {
				border: 1px solid var(--color-orange);
			}
		}

		&__btn {
			padding: var(--spacing-xs) var(--spacing-sm);
			border-radius: var(--border-radius-md);
			border: none;
			background-color: var(--color-orange);
			color: var(--color-light);
			transition: var(--transition);

			&:hover {
				background-color: var(--color-light-orange);
			}

			&:active {
				background-color: var(--color-orange);
			}
		}
	}
</style>
