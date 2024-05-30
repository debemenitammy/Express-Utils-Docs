---
sidebar_position: 1
---

# Server

Express Utils provides a convenient `Server` class to simplify server setup and management within your Express application. Here's a breakdown of its functionalities and usage:

## Benefits

- **Simplified server setup**: The Server class offers a concise way to configure and start your Express server.

- **Graceful shutdown**: It provides built-in functionality for gracefully shutting down your server, ensuring a clean termination process.

- **Customizable setup**: You can define optional setup functions to be executed before the server starts.

## Code Example

```TypeScript
import { Server } from "@obisiket1/express-utils";
import app from "./app"; // Replace with your Express app instance

Server.start({
  force: true,  // Optional: Forcefully shuts down any existing server on the port
  expressApp: app,  // Required: Your Express application instance
  onStart: ({ port }) => {  // Optional: Callback function executed when the server starts
    console.log("Server has started @", port);
  },
});
```

### Explanation:

- We import the `Server` class from express-utils.

- We import our Express application instance (`app`) from the appropriate file.

- We call the `Server.start` method, passing an options object:
  - `force`: (Optional) Set to `true` to forcefully shut down any existing server running on the port you intend to use.

  - `expressApp`: (Required) This property specifies your Express application instance.

  - `onStart`: (Optional) This callback function is executed once the server starts successfully. It receives an object containing the port number where the server is listening.


### Using the Server Class effectively

The `Server` class streamlines your server setup process and ensures a clean shutdown. Consider using the `force` option cautiously, as it might disrupt other applications using the same port. Remember to replace `./app` with the actual path to your Express application file.

The next sections will explore other core features of Express Utils and provide detailed explanations with code examples.