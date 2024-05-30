---
sidebar_position: 1
---

# Decorators (using useHTTPDecorator)

Express Utils primarily utilizes the `useHTTPDecorator` function to define route handlers and controllers within your Express.js application. Here's a breakdown of the key decorators provided:

##### `@Http.Controller()`

- **Description**: Marks a class as a controller, allowing you to define route handlers within its methods.
- **Syntax**: `@Http.Controller()`
- **Parameters**: None
- **Return Value**: None

**Example**:

```typescript
@Http.Controller()
export default class AuthController {
  // ... Define route handler methods here
}
```

&nbsp;

##### `@Http.Get(path?: string, options?: RouteOptions)`
- **Description**: Transforms a class method into a GET route handler for the specified path.
- **Syntax**: `@Http.Get(path?: string, options?: RouteOptions)`
- **Parameters**:
  - `path` (Optional): The path for the route. If not provided, defaults to the method name.
  - `options` (Optional): An object containing additional configuration options for the route handler.
- **Return Value**: None

**Example**:

```typescript
@Http.Get("/api")
public async index(req: Request, res: Response) {
  // ... GET route handler logic
}
```

&nbsp;

##### `@Http.Post(path?: string, options?: RouteOptions)`
- **Description**: Transforms a class method into a POST route handler for the specified path.
- **Syntax**: @Http.Post(path?: string, options?: RouteOptions)
- **Parameters**:
  - `path` (Optional): The path for the route. If not provided, defaults to the method name.
  - `options` (Optional): An object containing additional configuration options for the route handler.
- **Return Value**: None

Similar to `@Http.Get` with request and response objects available within the method.

&nbsp;

##### `@P.Query() query: Record<string, any>` (and other Parameter Decorators)
- **Description**: Decorates a method parameter to indicate it should retrieve query string parameters from the request.
- **Syntax**: `@P.Query() query: Record<string, any>` (Other decorators like `@P.Body()` and `@P.Param()` exist for different parameter types)
- **Parameters**:
- `query`: The name of the parameter that will hold the parsed query string object.
- **Return Value**: None

**Example**:

```typescript
@Http.Get("/users")
public async getUsers(@P.Query() query: { name?: string, limit?: number }) {
  // ... Access query string parameters using the 'query' object
}
```

Refer to the official Express Utils documentation for a complete list of available parameter decorators and their functionalities.