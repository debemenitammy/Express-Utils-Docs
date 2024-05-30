---
sidebar_position: 3
---

# CreateConfig

Express Utils provides a `createConfig` utility to streamline configuration management and validation within your application. Here's how to use it:

## Benefits

- **Centralized configuration**: The `createConfig` function allows you to define and access your application configuration from a central location.

- **Validation capabilities**: It offers optional validation functionalities to ensure your configuration adheres to expected data types and formats.

## Code Example

```typescript
import { createConfig } from "@obisiket1/express-utils";

export default createConfig({
  config: {
    port: 8080, // Your application port
    databaseUrl: process.env.DATABASE_URL, // Load from environment variable
    // Add other configuration options here
  },
});
```

### Explanation

- We import the `createConfig` function from `express-utils`.
- We call `createConfig` to define our application configuration, passing an object with a single property:
- `config`: This object contains key-value pairs representing your configuration settings.
  - You can define default values directly like the `port`.
  - You can access environment variables using `process.env.VARIABLE_NAME` for dynamic configuration.

### Using the Configuration

Once you've defined your configuration using `createConfig`, you can access these settings throughout your application code:

```typescript
import config from "./config"; // Assuming you export the default from the config file

console.log("Server listening on port:", config.port);
```

### Validation (Optional)

`createConfig` offers optional validation capabilities. You can define validation rules for your configuration options to ensure they meet specific criteria (e.g., data type, format). Refer to the official Express Utils documentation for detailed information on configuration validation.

### Benefits of Centralized Configuration

Using `createConfig` promotes a centralized approach to managing your application configuration. This simplifies access and modification of configuration settings while offering  optional validation for enhanced data integrity.

The next sections will explore other core features of Express Utils and provide detailed explanations with code examples.