---
sidebar_position: 2
---

# Logger

Express Utils offers a built-in `createLogger` utility to simplify adding logging functionalities to your application. Here's how to use it:

## Benefits

- **Centralized logging**: The `createLogger` function provides a central point for configuring and creating loggers within your application.

- **Configurable logging**: You can control the logging level (e.g., debug, info, error) through the configuration options.

## Code Example
```typescript
import { createLogger } from "@obisiket1/express-utils";

const logger = createLogger({
  scope: __filename,  // Optional: Sets the scope for the logger (usually the file path)
  logDebug: false,    // Optional: Disables debug level logging (defaults to true)
});
```

### Explanation

- We import the `createLogger` function from `express-utils`.
- We call `createLogger` to create a logger instance, passing an optional configuration object:
  - `scope`: (Optional) This property defines the scope for the logger, typically set to the filename of the module using it. It helps identify the source of log messages.
  - `logDebug`: (Optional) This property controls whether debug level messages are logged. By default, debug messages are logged. Setting it to `false` disables them.


## Using the Logger

Once you have a logger instance, you can use it to log messages at different levels (e.g., debug, info, error) throughout your application code:

```typescript
logger.debug("This is a debug message");
logger.info("Application started successfully");
logger.error("An error occurred: ", errorObject);
```

### Benefits of Centralized Logging

Using `createLogger` promotes centralized logging configuration and simplifies managing log messages across your application. You can define different logging levels and potentially integrate with external logging services for a more robust logging solution.

The next sections will explore other core features of Express Utils and provide detailed explanations with code examples.