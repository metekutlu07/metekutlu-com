<script lang="ts">
  import '../app.css';
  import homepage_video from '$lib/assets/videos/brickup-inside.mp4';
  import cvpage_video from '$lib/assets/videos/dome3.mp4';
  import { page } from '$app/stores';

  $: option =
    $page.url.pathname === '/'
      ? { src: homepage_video, class: 'opacity-50' }
      : { src: cvpage_video, class: 'opacity-25' };
</script>

<svelte:head>
  <title>Mete Kutlu</title>
</svelte:head>

<div class="h-screen">
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
  <div class="relative z-10 h-screen">
    <slot />
  </div>
</div>
