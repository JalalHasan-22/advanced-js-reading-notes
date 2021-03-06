# Class 32 Context API: Behaviors

---

**When you have multiple contexts, what component type should you use (class/function) and why?**

- I will use the function based component because it will give me more control on the contexts.

**What are some good use cases for using the Context API for global state?**

- Site settings context or theme context.

**How can you best test context?**

- Testing the Provider and Consumer Together.
- Testing a component with children that consume Context.

---

## Document the following Vocabulary Terms

**context**: a way to pass data through the component tree without having to pass props down manually at every level.

**useContext()**: React Hook.

---

## context api

- Context provides a way to pass data through the component tree without having to pass props down manually at every level.

**When to Use Context**

Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language. For example, in the code below we manually thread through a “theme” prop in order to style the Button component:

    class App extends React.Component {
    render() {
        return <Toolbar theme="dark" />;
    }
    }

    function Toolbar(props) {
    // The Toolbar component must take an extra "theme" prop
    // and pass it to the ThemedButton. This can become painful
    // if every single button in the app needs to know the theme
    // because it would have to be passed through all components.
    return (
        <div>
        <ThemedButton theme={props.theme} />
        </div>
    );
    }

    class ThemedButton extends React.Component {
    render() {
        return <Button theme={this.props.theme} />;
    }
    }

Using context, we can avoid passing props through intermediate elements:

    // Context lets us pass a value deep into the component tree
    // without explicitly threading it through every component.
    // Create a context for the current theme (with "light" as the default).
    const ThemeContext = React.createContext('light');

    class App extends React.Component {
    render() {
        // Use a Provider to pass the current theme to the tree below.
        // Any component can read it, no matter how deep it is.
        // In this example, we're passing "dark" as the current value.
        return (
        <ThemeContext.Provider value="dark">
            <Toolbar />
        </ThemeContext.Provider>
        );
    }
    }

    // A component in the middle doesn't have to
    // pass the theme down explicitly anymore.
    function Toolbar() {
    return (
        <div>
        <ThemedButton />
        </div>
    );
    }

    class ThemedButton extends React.Component {
    // Assign a contextType to read the current theme context.
    // React will find the closest theme Provider above and use its value.
    // In this example, the current theme is "dark".
    static contextType = ThemeContext;
    render() {
        return <Button theme={this.context} />;
    }
    }
