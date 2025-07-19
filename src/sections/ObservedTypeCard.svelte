<script>
    import { onMount } from "svelte";
    import TypeCard from "../lib/TypeCard.svelte";
  
    export let text1 = "";
    export let text2 = "";
  
    let visible = false;
    let el;
  
    onMount(() => {
      const observer = new IntersectionObserver(
        (entries, observer) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              visible = true;
              observer.unobserve(entry.target);
            }
          });
        },
        { threshold: 0.5 }
      );
  
      if (el) observer.observe(el);
    });
  </script>
  
  <div bind:this={el}>
    {#if visible}
      <TypeCard {text1} {text2} />
    {/if}
  </div>
  