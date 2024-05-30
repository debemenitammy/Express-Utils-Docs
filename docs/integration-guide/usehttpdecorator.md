---
sidebar_position: 0
---

# UseHTTPDecorator

The `useHTTPDecorator` function is a cornerstone of Express Utils. It provides a decorator-based approach for defining routes within your controllers, offering several advantages over the legacy `useDecorator`. Here's a breakdown of its benefits and usage:

## Benefits

- **Improved this variable access**: `useHTTPDecorator` ensures proper access to the `this` variable within your controller methods decorated with route definitions.

- **Simplified controller setup**: The extended class constructor is automatically instantiated within the `$register` static method, streamlining controller creation.

## Code Example

```typescript
import { useHttpDecorator } from "@obisiket1/express-utils";
import { Router } from "express";

const { BaseController, Http, P } = useHttpDecorator();

@Http.Controller() // Marks this class as a controller
export default class AuthCtrl extends BaseController(Router) {
  @Http.Get("/api") // Defines a GET route handler for /api
  public async index(@P.Query() query: Record<string, any>) {
    return {
      data: query,
    };
  }
}
```

### Explanation

- We import `useHttpDecorator` and `Router` from the respective packages.

- We destructure the required functionalities: `BaseController`, `Http`, and `P` from `useHttpDecorator`.

- The `@Http.Controller()` decorator marks the `AuthCtrl` class as a controller.

- The `@Http.Get("/api")` decorator defines a GET route handler for the `/api` path within the `index` method of the controller.

- The `@P.Query()` decorator on the `query` parameter indicates that it should retrieve query string parameters from the request.


### Registering the Controller

Once your controllers are defined using `useHTTPDecorator`, you can register them with your Express application:

```TypeScript
import { mount } from "@obisiket1/express-utils";
import express from "express";

const app = express();

// Register a single controller
app.use("/", mount(AuthCtrl));

// Register multiple controllers under a specific path
app.use("/v1", mount([Controller1, Controller2, ...ControllerN]));

// ... (Rest of your Express app setup)
```

Here, we import `mount` from `express-utils` and use it to register the `AuthCtrl` controller with the root path (`/`). You can also register multiple controllers under a specific path like `/v1` by providing an array of controllers to the `mount` function.

This approach simplifies route definition within your controllers using decorators. The `useHTTPDecorator` ensures proper access to the `this` variable and streamlines controller creation for a more efficient development experience.

The next sections will explore other core features offered by Express Utils and provide detailed explanations with code examples.