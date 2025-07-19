<script>
    let { text } = $props();
</script>

<div class="text-card">
    <div class="content">
        <p>{text}</p>
    </div>
    <img class="climate-chart" src="https://www.climate.gov/sites/default/files/styles/full_width_stretch_featured_image/public/2025-01/NOAA-billion-dollar-disasters-counts-by-month-1980-2024.png?itok=V31iQbef" alt="The rise of natural disasters in the U.S." />
    <p class="legend"> Month-by-month accumulation of billion-dollar disasters for each year on record. The colored lines represent the top 6 years for most billion-dollar disasters. The dark gray line shows the average. All other years are colored light gray. NOAA NCEI Billion-dollar Disasters webpage. </p>
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

    .climate-chart{
        display: block;             
        margin: 2rem auto;           
        max-width: 80%;              
        height: auto;                
        border-radius: 12px;         
        box-shadow: 0 4px 16px rgba(0, 0, 0, 0.1); 
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

