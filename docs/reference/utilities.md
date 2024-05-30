---
sidebar_position: 2
---

# Utilities

Express Utils provides additional utility functions to streamline development:


##### `createConfig(config: ConfigOptions)`
- **Description**: Helps manage and validate application configuration.
- **Syntax**: `createConfig(config: ConfigOptions)`
- **Parameters**:
  - `config`: An object containing key-value pairs representing your configuration settings. It can also define validation rules for each configuration option.
- **Return Value**: An object containing the validated configuration options.

**Example**:
```typescript
export default createConfig({
  config: {
    port: 8080,
    databaseUrl: process.env.DATABASE_URL,
  },
});

// Access configuration options:
console.log("Server listening on port:", config.port);
```


##### `useMailer({ ...options }) (Experimental)`
- **Description**: (Experimental Feature) Provides a basic implementation for handling email sending within your server-side application.
- **Syntax**: `useMailer({ ...options })`
- **Parameters**:
  - `options`: An object containing configuration options for the mailer functionality. This might include a sender object, template path, and potentially options for a custom template engine.
- **Return Value**: An object with functionalities for creating and sending emails.

Important Note: useMailer is currently considered experimental. Refer to the official Express Utils documentation for the latest updates and detailed information on its usage.

For a comprehensive understanding of all available decorators, refer to the official Express Utils documentation. It will provide detailed explanations for each decorator, including its syntax, parameters, return values, and any additional usage considerations.