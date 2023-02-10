## Setting up react redux environment

**Step 1:** Make a new file named "store.js" inside the "src" folder and write the following code in it
```
import { createStore, combineReducers, applyMiddleware, compose } from "redux";
import thunk from "redux-thunk";
import { composeWithDevTools } from "redux-devtools-extension";

const reducer = combineReducers({});

let initialState = {};

const middleWare = [thunk];

const store = createStore(
  reducer,
  initialState,
  composeWithDevTools(applyMiddleware(...middleWare))
);

export default store;

```
**Step 2:** Now go to the "index.js" file and update it according to the following code:
```
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import { Provider } from "react-redux";
import store from "./store";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <Provider store={store}>
    <App />
  </Provider>
);

```
**Redux:** In redux we have three things which are:\
**1- Actions:** Actions tell us ***What to do***\
**2- Reducers:** Reducers tell us ***How to do***\
**3- Store:** Store takes reducers and manages a store base from where any component can take any thing. It prevents prop drilling...\\

We also use ***constants*** to make the code clean and readable
