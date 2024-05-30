---
sidebar_position: 5
---

# UseDecorator

**Note**: While `useDecorator` is still functional, it's recommended to use the improved `useHTTPDecorator` described in section 4.1 for a more streamlined approach to defining routes. This section provides a reference for those familiar with `useDecorato`.

## Functionality

`useDecorator` offers a set of decorators for defining routes, middleware, and controllers within your Express application. Here's an overview of some commonly used decorators:

Decorators provided by `useDecorator`:


| Decorator      | Description                                      |
|------------------|-------------------------------------------------|
| `GlobalMiddleware` | The `GlobalMiddleware` decorator, as the name suggests, sets up a global middleware function that applies across all routes defined on the decorated class. It can optionally accept a `path` property to limit the middleware to specific routes. |
| `Get`             | The `Get` decorator transforms a method into a GET route handler. It can optionally accept an `options` object defining the path and additional middleware for the route. If no options are provided, the method name is used as the path. |
| `Post`            | The `Post` decorator transforms a method into a POST route handler. It can optionally accept an `options` object defining the path and additional middleware for the route. If no options are provided, the method name is used as the path. |
| `Success`        | (Likely) Used to send a successful response with a data object. Refer to the official Express Utils documentation for detailed usage. |


### Code Example

```typescript
import { Logger, useDecorator } from "@obisiket1/express-utils";
import { NextFunction, Request, Response, Router } from "express";

const { GlobalMiddleware, Success, Controller, Post } = useDecorator();

@GlobalMiddleware({ path: "/auth" }) // Applies middleware to all routes in this controller
export default class AuthController extends Controller(Router) {
  @Post() // Defines a POST route handler for the register method
  async register(req: Request, res: Response, next: NextFunction) {
    const result = {
      data: {
        test: "red",
        jesus: ["red", "green", "blue"],
      },
    };

    return Success(res, result); // Likely sends a successful response with the result object
  }
}
```

### Recommendation

While `useDecorator` is still functional, consider using the improved `useHTTPDecorator` for a more efficient and recommended approach to defining routes and controllers within your Express.js projects using TypeScript.