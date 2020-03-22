<script>
    import { closeModal } from "svelte-native"
    export let article
</script>

<frame>
    <page>
        <scrollView>
            <stackLayout class="article">
                <label class="h1" text="{article.title}" textWrap="{true}" />
                <label class="body" text="written by {article.author}" textWrap="{true}" />
                <textView class="primary space" text="{article.description}" textWrap="{true}" />
                <!--<button on:tap={goToURL} text="Read more"/> Hadde plan om å ha en "Read More" button for å kunne lese artikkelen i sin helhet.-->
                <image
                    class="img rounded"
                    src="{article.urlToImage}"
                    alt="article cover image"
                    stretch="fill" />
                
                <button on:tap={ () => closeModal() } text="close" />
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