<script>
  import { onMount } from 'svelte';
  import { createEventDispatcher } from 'svelte';

  export let animation = 'fade'; // Default animation
  export let rootMargin = '0px 0px -10% 0px'; // Default rootMargin
  let intersected = false;
  const dispatch = createEventDispatcher();

  function handleIntersection(entries) {
    if (entries[0].isIntersecting) {
      intersected = true;
      observer.disconnect();
      dispatch('intersect');
    }
  }

  let observer;
  let container;

  onMount(() => {
    observer = new IntersectionObserver(handleIntersection, {
      root: null,
      rootMargin,
      threshold: 0
    });
    observer.observe(container);
  });
</script>

<div bind:this={container} class:visible={intersected} class={animation}>
  {#if intersected}
    <slot />
  {/if}
</div>

<style>
  div {
    min-height: 100vh; /* Ensure it takes up space even before content loads */
    transition: opacity 1s ease-out, transform 1s ease-out;
  }

  .fade {
    opacity: 0;
  }
  .visible.fade {
    opacity: 1;
  }

  .slide-left {
    transform: translateX(100px);
    opacity: 0;
  }
  .visible.slide-left {
    transform: translateX(0);
    opacity: 1;
  }
  .slide-albums {
    transform: translateY(100px);
    opacity: 0;
  }
  .visible.slide-albums {
    transform: translateX(0);
    transition: opacity 1.5s ease-out, transform 1.5s ease-out;
    opacity: 1;
  }
  .slide-top {
    transform: translateY(100px);
    opacity: 0.5;
  }
  .visible.slide-top {
    transform: translateX(0);
    opacity: 1;
  }

  .slide-scale-down {
    transform: scale(1.3);
    opacity: 0;
  }
  .visible.slide-scale-down {
    transform: scale(1);
    transition: opacity 1.5s ease-out, transform 1.5s ease-out;
    opacity: 1;
  }
</style>
