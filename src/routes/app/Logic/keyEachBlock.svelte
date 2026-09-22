<script lang="ts">

	const emojis = {
		Apple: '🍎',
		Banana: '🍌',
		Carrot: '🥕',
		Doughnut: '🍩',
		Egg: '🥚'
	};

	let { nameKey } = $props()

	const emoji = emojis[nameKey]

</script>

<p>{emoji} = {nameKey}</p>