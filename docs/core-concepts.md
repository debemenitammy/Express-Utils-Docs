---
sidebar_position: 3
---

# Core Concepts

This section covers the core principles behind Express Utils and how it interacts with Express.js and TypeScript.

## Express.js Integration
Express Utils seamlessly integrates with Express.js, a popular web framework for building Node.js applications. It leverages TypeScript decorators to simplify and enhance route definitions within your Express controllers. 

Traditionally, Express.js defines routes through functions like `app.get` and `app.post`. Express Utils introduces decorators like `@Http.Get` and `@Http.Post` that can be applied directly to controller methods. This approach offers several benefits:

- **Improved Readability**: Decorators make your code more readable and self-documenting. By looking at a controller class, you can easily understand the available routes and their associated HTTP methods.

- **Maintainability**: Decorators promote better code organization and maintainability. They separate route logic from controller logic, making it easier to modify or reuse code.

- **Type Safety (with TypeScript)**: When using TypeScript, decorators enable type checking for route handlers. This helps catch potential errors early in the development process and improves overall code reliability.


## TypeScript Support
Express Utils is designed specifically for use with TypeScript. TypeScript is a superset of JavaScript that adds optional static typing to the language. This static typing allows for:

- **Improved Type Safety**: TypeScript catches potential type errors during compilation, preventing runtime issues and ensuring data integrity.

- **Enhanced Code Completion**: IDEs with TypeScript support offer better code completion and refactoring capabilities, streamlining your development workflow.

- **Increased Maintainability**: Static typing makes codebases easier to understand and maintain, especially for larger projects with multiple developers.

By leveraging TypeScript decorators, Express Utils allows you to define clean, maintainable, and type-safe routes within your Express.js applications.