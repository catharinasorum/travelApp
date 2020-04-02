# Svelte Native World Wide Travel News

This is a simple app for iOS/Android that uses <a href="https://newsapi.org/"></a> to fetch and display travel news from around the world. It is build using the <a href="https://svelte-native.technology/docs">Svelte-Native</a> framework to build a native application. Svelte-Native is build on top of <a href="https://www.nativescript.org/">Nativescript</a>, so you need to go through the setup guide there in order to install the TNS CLI tools.

## Set up and build
To test the project, run:
```html
npm install
tns run [ios|android]
```

## Project Structure

### App.svelte
This is the main entrance to the project. But this file only import the screens in the project, and sets up the bottom navigation

### ./screens/Articles.svelte
This file..
- fetches news-data
- shows an initial scrollable list of travel news from all over the world, using <a href='http://svelte-natice.technology/docs#scrollview'>scrollView</a>

### ./screens/Saved.svelte
This files is not totally ready. The plan was that this file could show an initial scrollable list of saved articles from the list on the other tab (Articles)

### ./modals/Article.svelte
This file is not totally ready. But this is a component via Svelte-Native's showModal() function. It is a simple article display that..
- displays more detailed information about the news article, which is sent from the main component as a prop.
- uses closeModal() to get back to the main screen.
The plan was to add a "save" button, so you could save this article to the "Saved" screen. And the other plan was to show a "Read more" button, which would take you to the original site of the article.