---
sidebar_position: 4
---

# Mail

**Disclaimer**: The `useMailer` functionality within Express Utils is currently considered experimental. This section provides a basic overview of its functionalities, but keep in mind that it might undergo changes or improvements in future releases.

## Functionality
`useMailer` offers a basic implementation for handling email sending within your server-side application. It allows you to define a mail sender and configure a template path for composing email content.

### Code Example

```typescript
class Sender implements ISender {
  send(mail: IMail): void {
    console.log("Sent!", mail);
  }
}

const { Mail } = useMailer({
  sender: new Sender(),
  templatePath: path.join(__dirname, "templates"),
});

Mail.create({
  template: "text", // Assuming your template name is "text"
  subject: "Hello",
  data: {
    name: "Treasure",
    first_name: "Obisike",
  }
}).send();
```

### Explanation

1. We define a class `Sender` that implements the `ISender` interface (likely defined in Express Utils). This class simulates sending the email and logs the mail object to the console.

2. We use `useMailer` to configure the mail functionality. It takes an options object:
  - `sender`: This property specifies the sender object responsible for sending the email.
  - `templatePath`: This property defines the path to the directory containing your email templates.

3. We call `Mail.create` to create a new email object, specifying the template name (`text`), subject line, and data to be included in the template.

4. Finally, we call `send` on the email object to trigger the sending process (which currently logs the email details in this example).

### Template Engine Support
`useMailer` offers flexibility by allowing you to integrate your own template engine or use the built-in `StringEngine`.

- **Default Option**: By default, `useMailer` uses a basic `StringEngine` that treats the template content as plain text.

- **Custom Template Engine**: You can define a custom `TemplateEngine` class that implements the `ITemplateEngine` interface (likely defined in Express Utils). This allows you to integrate a more sophisticated templating solution for dynamic email content generation.

#### Important Note

The `useMailer` functionality is experimental and might be subject to changes in future releases of Express Utils. Refer to the official documentation for the latest updates and detailed information on using email functionalities.


