# Svelte Scroll Typewriter

This package allows you to create a typewriter than starts when observed hasslefree!

## How to use:

### Prerequisites:

- Simply download the package with

```
npm i sveltescrolltypewriter
```

- Import it into the file which is required with

```javascript
import SvelteScrollTypewriter from SvelteScrollTypewriter
```

### The use:

A requirements are two variables in the script tag being:

```javascript
let furthestScrolled = 0;
let scroll = 0;
$: if (scroll > furthestScrolled) {
	furthestScrolled = scroll;
}
```

The following tag somewhere in the file:

```svelte
<svelte:window bind:scrollY={scroll} />
```

and for each typewriter, specific variables for binding, such as:

```svelte
let typewriter1;
let height1;
```

In your onMount function, place the following:

```svelte
	onMount(() => {
		height1 = typewriter1.getBoundingClientRect().top - 300;
    // do this for every height, eg height2, height3 etc.
	});
```

Then, place the following wherever desired. HEIGHT is a placeholder for the height variable, and PHRASE is a placeholder for your custom phrase:

```svelte
<div bind:this={typewriter1}>
<Typewriter
					height={height1}
					{furthestScrolled}
					phrase="PHRASE"
			/>
</div>
```

## Options:

- auto: boolean
	- This optional property specifies whether the typewriter should start automatically or not

- height: integer
	- This optional property specifies the distance from the top of the DOM and the typewriter in pixels

- furthestScrolled: integer
	- This optional property specifies the furthest distance that has been scrolled to in  pixels

- phrase: string
	- This mandatory property specifies the phrase that will be dispayed in the typewriter

- fontSize: integer
	- This optional property specifies the font size for the text


I apologise for the bloat, but the package works.

There is no stylign attatched to the typewriter, just plain text

Thank you for using my package :)
