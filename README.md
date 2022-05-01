## Instructions

Call the News API to populate a list of news articles using Redux Thunk
 
------------------------------------------------------------

* Look at the `state.js` file under the redux folder. You should see just one property called articles with an empty array present. We will populate (or replace) the array with data from the News API.

* In the `reducers.js` file you should see the current reducer function for "articles". Add a case for "FETCH_ARTICLES" that simply returns "action.value"

* In the `store.js` file you need to do three things:
    1. import `applyMiddleware`
    2. import `thunk`
    3. pass `applyMiddleware(thunk)` to the createStore function

* Finally (for the redux folder), in `actions.js`, fill the "fetchArticles" function so that it calls the API endpoint (with fetch) and then dispatches the "articleAction" action creator. You will need to pass `response.articles` (the result of the fetch call) to that action creator to fulfil the "articles" parameter.  The API endpoint to call is at the top of the file.

* Now, in our `List` container we should see that there is already a mapStateToProps function that is sending in the articles array. We need to make a mapDispatchToProps function that returns a property with key, `fetchArticles` and value `() => dispatch(fetchArticles())`. Remember to import the `fetchArticles` action at the top of the page.

* In the `List` _component_ we simply need to create a "componentDidMount" function and call "this.props.fetchArticles", which is the redux action we just connected. You should see a list of news articles appear on the page.