<script>
    let { text } = $props();

    let activeChart = $state('county');

  const showCounty = () => {
    activeChart = 'county';
  };

  const showState = () => {
    activeChart = 'state';
  };
</script>

<div class="text-card">

    <!-- Paragraph -->
    <div class="content">
        <p>{text}</p>
      </div>
    
    <!-- Buttons side by side -->
    <div class="button-container">
      <button onclick={showCounty} class:selected={activeChart === 'county'}>
        County View
      </button>
      <button onclick={showState} class:selected={activeChart === 'state'}>
        State View
      </button>
    </div>

    <!-- Images (conditional display) -->
    {#if activeChart === 'county'}
      <img class="county-chart" src=" " alt="project amount county map" />
    {/if}
  
    {#if activeChart === 'state'}
      <img class="state-chart" src=" " alt="project amount state map" />
    {/if}

    <img class="incident-chart" src=" " alt="incident type chart" />
  
    <!-- Legend -->
    <p class="legend">

    </p>
  </div>

<style>
    .text-card {
        background-color: #007052;
        height: 100vh;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }

    .content {
        max-width: 700px;
        background-color: #034c36;
        padding: 2rem;
        border: 6px solid #e3ff00;
        border-radius: 2rem;
        box-shadow: 16px 16px #188f70;
    }

    p {
        font-size: 1.3rem;
        color: #f7f5eb;
        margin-top: 1rem;
    }

    .legend{
        font-size: 0.7rem;
    }

    .county-chart{
        display: block;             
        margin: 2rem auto;           
        max-width: 80%;              
        height: auto;                
        border-radius: 12px;         
        box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1); 
    }
    .state-chart{
        display: block;             
        margin: 2rem auto;           
        max-width: 80%;              
        height: auto;                
        border-radius: 12px;         
        box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1); 
    }

    .button-container {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 1rem;
  }

  button {
    padding: 0.5rem 1rem;
    border: 2px solid #4096fa;
    border-radius: 5px;
    background: white;
    cursor: pointer;
    font-weight: bold;
  }

  button.selected {
    background: #4096fa;
    color: white;
  }

  img {
    width: 100%;
    border-radius: 8px;
    margin-top: 1rem;
    transition: opacity 0.5s ease;
  }
    

    @media (max-width: 600px) {

        .climate-chart{
            max-width: 95%;
            margin: 1.5rem auto;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>

