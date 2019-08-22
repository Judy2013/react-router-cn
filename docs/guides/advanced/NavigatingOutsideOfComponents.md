# 在组件外部使用导航

虽然在组件内部可以使用 `this.context.router` 来实现导航，但许多应用想要在组件外部使用导航。使用Router组件上被赋予的history可以在组件外部实现导航。

```js
import { createBrowserHistory as createHistory } from 'history
export const history = createHistory()
```

```js
// your main file that renders a Router
import { Router, BrowserRouter } from 'react-router'
import { history } from './app/history'
import routes from './app/routes'
render(<BrowserRouter><Router history={history} routes={routes}/></BrowserRouter>, el)
```

```js
// somewhere like a redux/flux action file:
import { history } from './app/history'
history.push('/some/path')
```
