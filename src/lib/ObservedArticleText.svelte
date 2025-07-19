<script>
    import { onMount } from "svelte";

    export let callback;
    export let options = { threshold: [0.9] };


    let uniqueId = Math.random().toString();
    let el;

    //let { children, callback, options } = $props();

    // this uniqueId just lets us target the element 
    // with `document.getElementById(uniqueId)` later on.
    // it's a little hacky, but it works. 

    // here we define the onMount() function for this component.
    // svelte handles calling the onMount() function *after* all of the HTML in this
    // component has been mounted to the DOM. we have to put the intersection observer
    // stuff in onMount() because we need to target the <div> we create below,
    // but it won't actually exist in the DOM until it's been mounted. 

    //onMount(() => {
        //let intersectionObserver = new IntersectionObserver(callback, options);

        //const observedElement = document.getElementById(uniqueId);
        //intersectionObserver.observe(observedElement);
    //});

    onMount(() => {
    const observer = new IntersectionObserver(callback, options);
    if (el) observer.observe(el);

    return () => {
      if (el) observer.unobserve(el);
      observer.disconnect();
    };
  });

</script>

<!-- assign the containing div the id `uniqueId` so we can target it -->
<div bind:this={el} data-id={uniqueId} class="article-text">
    <p><slot /></p>
  </div>
  
<style>
    .article-text {
        margin: 50vh auto;
        width: 50%;
        background-color: #ff99fc;
        color: #007052;
        border: solid #8427c9 3px;
        border-radius: 20px;
        padding: 20px;
        box-shadow: 16px 16px #8aa6df;
    }
</style>
