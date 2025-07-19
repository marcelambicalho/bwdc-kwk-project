<script>
    import ObservedTypeCard from "./ObservedTypeCard.svelte";
    import BWDCTableau from "../lib/BWDCTableau.svelte";
    
  
    const text1 = "These systems have been around for a long time, being updated as disasters become more and more destructive and unpredictable. But are these projects being applied and distributed equally amongst those in need?";
    const text2 = "When analyzing race equity indicators, we already know of the significant number of black communities that are socially vulnerable to disasters.";

  </script>
  
  
  <ObservedTypeCard text1={text1} />
  <ObservedTypeCard text1={text2} />
  <BWDCTableau url="https://public.tableau.com/shared/8GFYDHZF6?:display_count=n&:origin=viz_share_link&:embed=y" />
  
  