<script lang="ts">
	export let elem_id: string = "";
	export let elem_classes: Array<string> = [];
	export let visible: boolean = true;
</script>

<div 
	id={elem_id}
	class='gr-group {elem_classes.join(" ")}' 
	class:hide={!visible}
>
	<div class="styler"
	style:--block-radius="0px"
	style:--block-border-width="0px"
	style:--layout-gap="1px"
	style:--form-gap-width="1px"
	style:--button-border-width="0px"
	style:--button-large-radius="0px"
	style:--button-small-radius="0px"
>
	<slot />
	</div>
</div>

<style>
	div {
		border: var(--block-border-width) solid var(--border-color-primary);
		background: var(--border-color-primary);
		border-radius: var(--block-radius);
		display: flex;
		flex-direction: column;
		gap: var(--form-gap-width);
		overflow: hidden;
	}
	div > :global(*:not(.absolute)) {
		border: none;
		border-radius: 0;
	}
	.hide {
		display: none;
	}
</style>