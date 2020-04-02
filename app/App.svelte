<script>
    import Articles from './screens/Articles.svelte'
    import Saved from './screens/Saved.svelte'
</script>

<page actionBarHidden={true}>
   <tabs tabsPosition="bottom">
        <tabStrip>
            <tabStripItem title="Articles" />
            <tabStripItem title="Saved" />
        </tabStrip>

        <tabContentItem>
            <frame>
                <Articles />
            </frame>
        </tabContentItem>

        <tabContentItem>
            <frame>
                <Saved />
            </frame>
        </tabContentItem>
    </tabs>
</page>