<script>
import { onMount } from "svelte"
import { showModal } from "svelte-native"
import Article from "./modals/Article.svelte"

const api = "5601425ba11d4e97bc73a41da921ee79"
const subject = "travel" // har subject = travel for å få med nyheter innen reiseliv

const getData = () => {
    const url = `https://newsapi.org/v2/everything?q=${subject}&language=en&apiKey=${api}` // har tatt alle nyheter med søkeordet "travel"
    fetch(url)
        .then(response => response.json())
        .then(json => {
            articles = json.articles
        })
        .catch(error => console.log(error))
}

let articles = []

onMount(() => {
    getData()
})

const showArticle = async (article) => {
    await showModal({
        page: Article,
        props: {
            article:article
        }
    })
}
</script>

<page>
    <actionBar title="World Wide Travel News" flat="true" />
    <stackLayout>

        <scrollView>
            <stackLayout class="articles">
                {#each articles as article}
                    <stackLayout
                        on:tap={ () => showArticle(article)} 
                        class="article">
                        <image class='img-rounded' src='{article.urlToImage}' alt='cover' stretch='aspectFill' />
                        <label textWrap="{true}" class="h2 text-center" text="{article.title}" />
                    </stackLayout>
                {:else}
                    <label text="Loading" />
                {/each}
            </stackLayout>

        </scrollView>

    </stackLayout>
</page>


<style>
    .articles{
        width: 100%;
    }

    .article{
        min-height: 100;
        padding: 24;
        margin: 24;
        background-color: #eee;
    }
</style>
