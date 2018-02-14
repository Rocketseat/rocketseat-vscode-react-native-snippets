# React Native Code Snippets for VS Code

## Summary

* [Installation](#installation)
* [Usage](#usage)
  * [Component](#component)
  * [ESLint](#eslint)
  * [Redux](#redux)
  * [Reactotron](#reactotron)
  * [Babel](#babel)
  * [Apisauce](#apisauce)

### Installation

To install Snippets on OSX, paste `javascript.json` file in:

`/Users/<your_user>/Library/Application Support/Code/User/snippets/`

To install Snippets on Windows, paste `javascript.json` file in:

`C:\Users\<your_user>\AppData\Roaming\Code\User\snippets`

## Usage

### Component

#### [rnc] - Create React Native Stateful Component

```javascript
import React, { Component } from 'react';

import { View } from 'react-native';

// import styles from './styles';

export default class MyComponent extends Component {
  render() {
    return (
      <View />
    );
  }
}
```

#### [rnstc] - Create React Native Stateless Component

```javascript
import React from 'react';

import { View } from 'react-native';

// import styles from './styles';

const MyComponent = () => (
  <View />
);

export default MyComponent;
```

#### [styles] - Create Styles File

```javascript
import { StyleSheet } from 'react-native';
// import { colors, fonts, metrics } from 'styles';

const styles = StyleSheet.create({});

export default styles;
```

#### [proptypes] - Create Stateful Component PropTypes

```javascript
static propTypes = {};
```

#### [defaultprops] - Create Stateful Component DefaultProps

```javascript
static defaultProps = {};
```

#### [render] - Create Stateful Component render method

```javascript
render() {
  return (
    <View />
  );
}
```

### ESLint

#### [eslint] - Create ESLint file config

```json
{
  "parser": "babel-eslint",
  "env": {
    "browser": true,
    "jest": true
  },
  "plugins": ["react-native", "jsx-a11y", "import"],
  "extends": ["airbnb", "plugin:react-native/all"],
  "rules": {
    "react/jsx-filename-extension": [
      "error",
      { "extensions": [".js", ".jsx"] }
    ],
    "global-require": "off",
    "no-console": "off",
    "import/prefer-default-export": "off",
    "no-unused-vars": ["error", { "argsIgnorePattern": "^_" }]
  },
  "settings": {
    "import/resolver": {
      "babel-module": {}
    }
  },
  "globals": {
    "__DEV__": true
  }
}
```

### Redux

#### [reduxSetup] - Create Redux Setup file

```javascript
import { combineReducers } from 'redux';

/* Reducers */
// import navReducer from 'navigation/reducer';

import configureStore from './configureStore';
// import rootSaga from './sagas';

export default () => {
  const rootReducer = combineReducers({
    // nav: navReducer,
  });

  return configureStore(rootReducer, rootSaga);
};
```

#### [configureStore] - Create Configure Store file

```javascript
import { createStore, applyMiddleware, compose } from 'redux';

export default rootReducer => {
  const middleware = [];
  const enhancers = [];

  /* Saga */
  // const sagaMonitor = __DEV__ ? console.tron.createSagaMonitor() : null;
  // const sagaMiddleware = createSagaMiddleware({ sagaMonitor });
  // middleware.push(sagaMiddleware);

  enhancers.push(applyMiddleware(...middleware));

  /* Store */
  const createAppropriateStore = __DEV__
    ? console.tron.createStore
    : createStore;
  const store = createAppropriateStore(rootReducer, compose(...enhancers));

  /* Run Saga */
  // sagaMiddleware.run(rootSaga);

  return store;
};
```

#### [reduxComponent] - Create React Native Stateful Redux Component

```javascript
import React, { Component } from 'react';

import { View } from 'react-native';

import { connect } from 'react-redux';

// import styles from './styles';

class MyComponent extends Component {
  render() {
    return (
      <View />
    );
  }
}

const mapStateToProps = state => ({});

const mapDispatchToProps = dispatch => ({});

export default connect(mapStateToProps, mapDispatchToProps)(MyComponent);
```

#### [reduxComponent] - Create React Native Stateless Redux Component

```javascript
import React from 'react';

import { View } from 'react-native';

import { connect } from 'react-redux';

// import styles from './styles';

const MyComponent = () => (
  <View />
);

const mapStateToProps = state => ({});

const mapDispatchToProps = dispatch => ({});

export default connect(mapStateToProps, mapDispatchToProps)(MyComponent);
```

#### [mapStateToProps] - Create Redux MapStateToProps

```javascript
const mapStateToProps = state => ({});
```

#### [mapDispatchToProps] - Create Redux MapDispatchToProps

```javascript
const mapDispatchToProps = dispatch => ({});
```

#### [duck] - Create React Native Duck Module

```javascript
import { createReducer, createActions } from 'reduxsauce';
import Immutable from 'seamless-immutable';

/* Types & Action Creators */

const { Types, Creators } = createActions({
  // actionType: ['dataPassed'],
});

export const TesteTypes = Types;
export default Creators;

/* Initial State */

export const INITIAL_STATE = Immutable({
  // data: [],
});

/* Reducers */

// export const reducer = state =>
//   state.merge({ data: [] });

/* Reducers to types */

export const reducer = createReducer(INITIAL_STATE, {
  // [Types.ACTION_TYPE]: reducer,
});
```

### Reactotron

#### [reactotronconfig] - Create Reactotron Config

```javascript
import Reactotron from 'reactotron-react-native';

if (__DEV__) {
  const tron = Reactotron
    .configure()
    .useReactNative()
    .connect();

  tron.clear();

  console.tron = tron;
}
```

### Babel

#### [moduleResolver] - Create Module Resolver config

```json
{
  "presets": ["react-native"],
  "plugins": [
    [
      "module-resolver",
      {
        "cwd": "babelrc",
        "root": ["./src"],
        "extensions": [".js", ".ios.js", ".android.js"]
      }
    ]
  ]
}
```

### Apisauce

#### [apisauce] - Create APISauce Config

```javascript
import { create } from "apisauce";

const api = create({
  baseURL: "http://localhost:3000",
});

export default api;
```
