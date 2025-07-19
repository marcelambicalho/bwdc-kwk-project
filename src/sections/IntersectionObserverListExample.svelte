<script>
    import { slide, blur } from "svelte/transition";
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
  
    const fullList = [

        "Hazard Mitigation Assistance Grants", 
        "Infrastructure and Repair Programs", 
        "Individual Emergency Aid (water, food, childcare, etc)", 
        "Individual Housing and Shelter Projects", 
        "More Here"

        ];
    let itemsToShow = 0;
    const triggeredSet = new Set();
    const options = { threshold: [0.9] };
  
    const callback = (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const id = entry.target.getAttribute("data-id");
          if (!triggeredSet.has(id) && itemsToShow < fullList.length) {
            triggeredSet.add(id);
            itemsToShow = itemsToShow + 1;
          }
        }
      });
    };
  </script>
  
  <div>
    <Scroller layout="left">
      {#snippet sticky()}
        <div id="lists-container">
          <div class="list">
            <h3> Projects and Programs </h3>
            {#each fullList.slice(0, itemsToShow) as item, index (item)}
                <div
                    class="list-item"
                        in:slide={{ duration: 750 }}
                        out:blur={{ duration: 1000 }}
                >
            {#if item === "More Here"}
                <a href="https://www.fema.gov/assistance" target="_blank" rel="noopener noreferrer">
            {item}
                 </a>
            {:else}
        {item}
    {/if}
  </div>
{/each}

          </div>
        </div>
      {/snippet}
  
      {#snippet scrolly()}
        <ArticleText>
          Consequently, in the U.S. there are several initiative that aim to
          <strong>tackle the causes and consequences</strong> of those disasters, either nationally or locally. 
        </ArticleText>
  
        <!-- CUSTOM SCROLLY TEXT BLOCKS -->
        <ObservedArticleText {callback} {options}>
          At a national level, the government has an obligation to provide grants and financial contributions to state-level or county-level governments for general efforts after a disaster. That money is used according to what is mostly needed at that moment. 
        </ObservedArticleText>
  
        <ObservedArticleText {callback} {options}>
          Ranging from building shelters to barriers and other systems that prevent flooding, wildfires, earthquake damages, etc. These also go towards rebuilding areas affected by natural disasters (hostpitals, schools, houses, and others.)
        </ObservedArticleText>
  
        <ObservedArticleText {callback} {options}>
          Local government and community initiatives, but that must propose projects that align with federal criteria. Can be a call for donations or civilians that help ration food, organise shelters, create search groups for survivors, etc. 
        </ObservedArticleText>
  
        <ObservedArticleText {callback} {options}>
          Also led locally and very present in NGOs, housing projects are initiatives to provide shelter-related items (furniture, supplies, etc) or actual shelter from community locations (gymnasiums, other people's houses, etc.)
        </ObservedArticleText>
  
        <ObservedArticleText {callback} {options}>
         Click the box to check for other resources available for after natural disasters. 
        </ObservedArticleText>
      {/snippet}
    </Scroller>
  </div>
  

<style>
    #lists-container {
        display: flex;
        position: fixed;
        flex: 1 1; /* Allows growing, shrinking */
        width: 100%;
    }

    .list {
        margin: 0px 20px;
        background-color: #ff99fc;
        color: #8427c9;
        border: solid #8427c9 3px;
        border-radius: 20px;
        box-shadow: 16px 16px #8aa6df;
        width: 100%;
    }

    .list-item {
        background-color: #e3ff00;
        color: #8427c9;
        border: solid #8427c9 3px;
        border-radius: 20px;
        padding: 10px;
        width: 50%;
        margin: 5px auto;
        text-align: center;
    }

    h3 {
        text-align: center;
    }
</style>
