<script>
    export let text1 = "";
    export let text2 = "";
  
    let displayed1 = "";
    let displayed2 = "";
  
    const typeSpeed = 20; // ms per character
  
    // typewriter effect for each line
    const typeText = (text, setter) => {
      let i = 0;
      const interval = setInterval(() => {
        setter(text.slice(0, i + 1));
        i++;
        if (i === text.length) clearInterval(interval);
      }, typeSpeed);
    };
  
    $: if (text1) typeText(text1, t => displayed1 = t);
    $: if (text2) typeText(text2, t => displayed2 = t);
  </script>
  
  <div class="text-card">
    {#if text1}
      <div class="txt-1">
        <p>{displayed1}</p>
      </div>
    {/if}
    {#if text2}
      <div class="txt-2">
        <p>{displayed2}</p>
      </div>
    {/if}
  </div>
  
  <style>
    .text-card {
        background-color: #007052;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }
  
    .txt-1, .txt-2 {
        max-width: 700px;
        background-color: #034c36;
        padding: 2rem;
        border: 6px solid #e3ff00;
        border-radius: 2rem;
        box-shadow: 16px 16px #188f70;
        color: white

    }
  </style>
  