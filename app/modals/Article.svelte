<script>
    import { closeModal } from "svelte-native" // for å lukke <frame>
    export let article 

    let savedArticles = []
</script>

<frame>
    <page>
        <scrollView>
            <stackLayout class="article">
                <label class="h1" text="{article.title}" textWrap="{true}" />
                <label class="body" text="written by {article.author}" textWrap="{true}" />
                <label class="primary space" text="{article.description}" textWrap="{true}" />
                <image
                    class="img rounded"
                    src="{article.urlToImage}"
                    alt="article cover image"
                    stretch="fill" />
                
                <button on:tap={ () => closeModal() } text="close" /> <!-- on:tap = lukker article.svelte-->
                
            </stackLayout>
        </scrollView>
    </page>
</frame>

<style>
    .article {
        padding: 44;
    }
    .space {
        margin: 30 0;
        line-height: 5;
    }
</style>