# Tutorial - Router

Next we import [Router](../api/Router), render it, and render our [Route Components](../api/Route-Component) as children. All that's left is to add a `path` prop to each child. Congratulations, you’ve successfully integrated Reach Router.

```jsx
import { Link, Router } from "@reach/router"

// under the `nav`
<Router>
  <Home path="/" />
  <Dashboard path="/dashboard" />
</Router>
```
