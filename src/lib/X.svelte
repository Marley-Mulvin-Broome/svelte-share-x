<script lang="ts">
	import { ShareButton } from "@svelte-share/button";

	/**
	 * The url to share
	 */
	export let url: string;

  /**
   * The text to write on the Tweet/X (Do people call them Xs?)
   */
  export let text: string = "";

  /**
   * List of hashtags to include in the post.
   * Do not include the '#' character itself.
  */
  export let hashtags: string[] = [];

  /**
   * A username to attribute the Tweet to.
   */
  export let via = '';

  /**
   * 
   */
  export let related = '';

	/**
	 * Accessibility label that will be shown on the parent <a> tag.
	 */
	export let ariaLabel = 'Share on X';

	/**
	 * Whether to display the icon
	 */
	export let showIcon = true;

	let classes = '';

	export { classes as class };

	$: href = encodeURI(`https://x.com/intent/tweet/?text=${text}&hashtags=${hashtags.join(',')}&via=${via}&related=${related}&url=${url}`);
</script>

<ShareButton
	url={href}
	{ariaLabel}
	class={classes}
	{showIcon}
>
		<svg slot="icon" width="25" height="23" viewBox="0 0 25 23" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path
          d="M19.38 0.622803H23.06L14.98 9.79481L24.42 22.2368H17.012L11.212 14.6759L4.57199 22.2368H0.891987L9.45199 12.4268L0.411987 0.622803H8.00399L13.244 7.52972L19.38 0.622803ZM18.092 20.0834H20.132L6.93199 2.69647H4.73999L18.092 20.0834Z"
          fill="white"
        />
      </svg>

	<slot />
</ShareButton>

<style>
	svg {
		width: var(--share-icon-width, 2em);
		height: var(--share-icon-height, 2em);
	}
</style>