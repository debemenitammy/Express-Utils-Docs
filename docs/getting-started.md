---
sidebar_position: 2
---

# Getting Started

This section provides a quick introduction to using Express Utils in your TypeScript project.

## Basic Usage

Here's a simple example demonstrating how to import and use the `@Http.Get` decorator from Express Utils to define a basic route handler:

```typescript
import { Router } from "express";
import { Http } from "@obisiket1/express-utils";

const router = new Router();

@Http.Controller() // Marks this class as a controller
export default class MyController {
  @Http.Get("/hello") // Defines a GET route handler for /hello
  public async helloWorld(req: any, res: any) {
    return res.send("Hello World!");
  }
}
```
This code example does the following:
- Imports the `Router` class from Express and the `Http` namespace from Express Utils. 
- Creates a new router instance and decorate a class named `MyController` with `@Http.Controller()`. - Marks the class as a controller for handling routes.  
- Defines a route handler method `helloWorld` inside the controller, decorated with `@Http.Get("/hello")`. 
This tells Express Utils to map this method to an HTTP GET request for the `/hello` path. The method simply sends the string "Hello World!" as a response.

## Key Features

- **Use decorators to define routes**: Express Utils leverages decorators to simplify route definitions within your controllers.

- **Improved type safety**: By using TypeScript with decorators, you benefit from improved type safety and better code maintainability.

- **Built-in middleware support**: Express Utils provides decorators for defining global and route-specific middleware functionalities.

- **Server class**: The package offers a `Server` class for streamlined server setup and graceful shutdown.

- **Logging utility**: A built-in logger simplifies adding logging capabilities to your application.

- **Configuration management**: The `createConfig` function assists with managing and validating configuration settings.

- **Experimental Mail functionality**: (**Note**: This feature is experimental) The package provides a basic implementation for handling mail sending within your server.

- **Template engine agnostic Mailer**: The `useMailer` function allows integrating various template engines for email content.

This brief overview introduces some of the core functionalities offered by Express Utils.  The following sections will delve deeper into each feature and provide detailed explanations and usage examples.