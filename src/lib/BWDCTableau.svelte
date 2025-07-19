<script>
    import { onMount } from "svelte";
  
    export let url;
    export let width = "100%";
    export let height = "800px";
  
    let container;
  
    onMount(() => {
      const script = document.createElement("script");
      script.src = "https://public.tableau.com/javascripts/api/tableau-2.min.js";
  
      script.onload = () => {
        // Safe access of window.tableau even if it's not typed
        const tableau = window.tableau;
        if (tableau && container) {
          new tableau.Viz(container, url, {
            width,
            height,
            hideTabs: true,
            hideToolbar: false,
          });
        }
      };
  
      document.body.appendChild(script);
    });
  </script>
  
  <div bind:this={container} class="tableau-chart"></div>
  
  <style>
    .tableau-chart {
      max-width: 1200px;
      margin: 2rem auto;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 0 12px rgba(0, 0, 0, 0.1);
    }
  </style>
  