# MAUI-sandbox

## .NET MAUI Project Structure

### Folders

- **Platforms/** — Contains code and settings for different operating systems, such as Android, iOS, and Windows.
- **Properties/** — Contains application settings, such as how the app runs during development.
- **Resources/** — Stores images, fonts, icons, and other files used in the app.

### Important Files

- **MainPage.xaml** — Defines what the main page looks like (buttons, text, layouts, etc.).
- **MainPage.xaml.cs** — Contains C# code that controls what happens on the main page, such as button clicks.
- **App.xaml** — Defines shared application resources, such as colors and styles.
- **App.xaml.cs** — Sets up the application when it starts.
- **AppShell.xaml** — Defines the application's navigation structure.
- **AppShell.xaml.cs** — Contains C# code related to AppShell.
- **MauiProgram.cs** — Configures the application and its services before it starts.
- **MauiSandbox.csproj** — Project configuration file. Defines the target platforms, .NET version, and required packages.

### Quick Reminder

- **XAML** = What the user sees.
- **C#** = How the application behaves.
- **Resources** = Files used by the application.
- **Platforms** = Platform-specific settings and code.

## What runs when the app starts

1. **Platform** — The operating system launches the app.
2. **MauiProgram.cs** — Prepares and configures the app.
3. **App.xaml / App.xaml.cs** — Creates the app and loads shared resources.
4. **AppShell.xaml / AppShell.xaml.cs** — Sets up navigation and chooses the first page.
5. **MainPage.xaml / MainPage.xaml.cs** — Displays the main page and its content.

**In simple terms:** The operating system starts the app → MAUI prepares it → App creates it → AppShell handles navigation → MainPage shows the interface.

## What is XAML?

**XAML (Extensible Application Markup Language)** is used to create user interfaces in .NET MAUI.

- Similar to HTML, but XAML elements represent **.NET objects**.
- Each XAML tag creates an object, such as a button, label, or layout.
- Attributes define the object's properties, such as text, color, or size.
- Elements can be nested inside other elements (parent-child relationship).
- XAML allows us to build interfaces without manually creating every object in C#.

### Example

```xml
<Label Text="Hello World" />
```

This is similar to writing in C#:

```csharp
Label myLabel = new Label();
myLabel.Text = "Hello World";
```

**In short:** XAML describes the interface, and MAUI creates the corresponding .NET objects.

> NOTE: **XAML** is a declarative.  
> Declarative programming — describes what the result should look like, without specifying every step needed to create it.
>
> XAML is declarative because we describe UI elements and their properties, while MAUI handles their creation.

Compare:

| C# (Imperative) | XAML (Declarative) |
|---|---|
| Describes **how** to create an object, step by step. | Describes **what** the result should look like. |
| `Label myLabel = new Label();` | `<Label Text="Hello World" TextColor="Blue" />` |
| `myLabel.Text = "Hello World";` | MAUI creates the object and sets its properties automatically. |
| `myLabel.TextColor = Colors.Blue;` | No need to write each step manually. |