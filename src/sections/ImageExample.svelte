<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class="duck-img" src=" " alt="NPA Grants Graph" />
            <img class="duck-img" src=" " alt="NPA Infrastructure Graph" />
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>
                    We can also take a closer look at National vs Individual Programs in those areas: 
                </strong>
            </ArticleText>

            <ArticleText> Although National Programs seem more largely available accross counties, Infrastructure efforts seem lower on vulnerable areas of black homeowners. This means that, in teh areas most affected by natural disasters, the biggest concentration of black people that own property have a <strong> lesser chance at rebuilding.</strong></ArticleText>
        {/snippet}
    </Scroller>
</div>

<style>
    .duck-img {
        width: 25%;
        margin: 0px auto;
    }
</style>
