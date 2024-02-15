<script>
	export let height;
	export let furthestScrolled;
	export let auto = false;

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
		<p>{typedChar}</p>
	</section>
</main>

<style>



	p {
		font-size: 1.2rem;
		line-height: 150%;
    color: white;
    text-align:left;
	}
</style>
