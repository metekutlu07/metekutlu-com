<script lang="ts">
  import '../app.css';
  import homepage_video from '$lib/assets/videos/brickup-inside.mp4';
  import cvpage_video from '$lib/assets/videos/dome3.mp4';
  import type { LayoutData } from './$types';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';
  import { debounce } from '$lib/utils';

  export let data: LayoutData;

  $: option =
    data.currentPath === '/'
      ? { src: homepage_video, class: 'opacity-50' }
      : { src: cvpage_video, class: 'opacity-25' };

  const setViewHeight = () => {
    // fix full screen issue in mobile devices with 100vh
    let vh = window.innerHeight * 0.01;
    document.documentElement.style.setProperty('--vh', `${vh}px`);
  };

  const debouncedSetViewHeight = debounce(setViewHeight, 50);

  onMount(() => {
    debouncedSetViewHeight();
    window.addEventListener('resize', debouncedSetViewHeight);

    return () => {
      window.removeEventListener('resize', debouncedSetViewHeight);
    };
  });
</script>

<svelte:head>
  <title>Mete Kutlu</title>
</svelte:head>

{#key data.currentPath}
  <div class="full-height" in:fade={{ duration: 200 }} out:fade={{ duration: 100 }}>
    <video
      autoplay
      loop
      muted
      playsinline
      src={option.src}
      class="pointer-events-none fixed inset-0 h-full w-full object-cover {option.class}"
    >
      <track kind="captions" />
    </video>
    <div class="full-height relative z-10">
      <slot />
    </div>
  </div>
{/key}

<style lang="postcss">
  .full-height {
    height: 100vh;
    height: calc(var(--vh, 1vh) * 100);
  }
</style>
