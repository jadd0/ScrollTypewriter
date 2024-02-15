<script>
	export let height = 0;
	export let furthestScrolled = 0;
	export let auto = false;
	export let fontSize = 15;

	$: if (furthestScrolled >= height && !isTyping) {
		typing();
	}

	
	export let phrase = ''; 
	let typedChar = '';
	let index = 0;
	let typewriter; 

	let isTyping = false;

	const typeChar = () => {
		if (index < phrase.length) {
			isTyping = true;
			typedChar += phrase[index];
			index += 1;
		} else {
			return;
		}
	}

	const typing = () => (typewriter = setInterval(typeChar, 20));

	if (auto) {
		typing()
	}
</script>

<main>
	<section>
		<p style="font-size: {fontSize}px !important">{typedChar}</p>
	</section>
</main>

<style>
	p {
		line-height: 150%;
    color: white;
    text-align:left;
	}
</style>
