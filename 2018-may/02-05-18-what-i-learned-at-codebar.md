## What I learned at codebar 02/05/18

* **redux-thunk** - action creator that returns a function to perform asynchronous dispatch

  * without using this and trying to do a dispatch in an async action function it didn't work bringing this error:
  * _Actions must be plain objects. Use custom middleware for async actions_
  * beforehand it worked because we dispatched an actual object:

  ```js
  function getArticles(query) {
    return function(dispatch) {
      return fetch(
        `http://content.guardianapis.com/search?q=${query}&api-key=${API_KEY}`
      )
        .then(response => response.json())
        .then(data => {
          dispatch({
            type: SET_ARTICLES,
            articles: data.response.results
          });
        });
    };
  }
  ```

  * but if you want to dispatch a function that returns the object like the one below:

  ```js
  function getArticles(query) {
    return function(dispatch) {
      return fetch(
        `http://content.guardianapis.com/search?q=${query}&api-key=${API_KEY}`
      )
        .then(response => response.json())
        .then(data => {
          dispatch(receivedArticles(data.response.results))
        });
    };
  }
  ```

  * you will need to add redux-thunk in the central store like so:

  ```js
  import { createStore, applyMiddleware } from "redux";
  import thunk from "redux-thunk";
  import reducers from "../reducers";

  const store = createStore(reducers, applyMiddleware(thunk));

  export default store;
  ```

* **previously we dispatched the action directly** in the container where we're doing mapDispatchToProps but we can actually extract this into a function in the actions folder e.g.

```js
export function inputValue(text) {
  return {
    type: SEARCH_INPUT_VALUE,
    text
  };
}
```

* Also learned that controlled components such as `<input>` maintain their own state so if we also controlling this with state elsewhere we need to choose between the 2. This was the error message when I had `<input type="text" value={props.value} onChange={props.handleChange} />`:
  * *A component is changing a controlled input of type text to be uncontrolled. Input elements should not switch from controlled to uncontrolled (or vice versa). Decide between using a controlled or uncontrolled input element for the lifetime of the component.*
