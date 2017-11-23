import { createStore, applyMiddleware, compose } from 'redux'
import { routerMiddleware } from 'react-router-redux'
import thunk from 'redux-thunk'
import createHistory from 'history/createBrowserHistory'
import rootReducer from './modules'

export const history = createHistory();

const initialState = {};
const enhancer = [];
const middleware = [
  thunk,
  routerMiddleware(history)
]

if(process.env.NODE_ENV === 'development'){
  const devToolsExtension = window.devToolsExtension;
  if(typeof devToolsExtension === 'function'){
    enhancer.push(devToolsExtension());
  }
}

const composedEnhancers = compose(
  applyMiddleware(...middleware),
  ...enhancer
)

export default createStore(
  rootReducer,
  initialState,
  composedEnhancers
)
