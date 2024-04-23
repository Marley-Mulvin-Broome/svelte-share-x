# @svelte-share/line

Simple svelte component for sharing to X (Twitter).

## Usage

```svelte
<script lang="ts">
	import { X } from '@svelte-share/x';
</script>

<X
	url="https://www.marley-web.dev"
	text="Visit my website if you're cool!"
	hashtags={['developer', 'npm', 'nodejs']}
	via="marley_eng"
	related="npmjs"
	ariaLabel="Share on X"
	showIcon
>
	<span class="share-text"> Post </span>
</X>

<style>
	.share-text {
		font-size: 1.3em;
	}
</style>
```
