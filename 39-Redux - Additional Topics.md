# Redux - Additional Topics

## Redux Toolkit

Redux Toolkit is the official, opinionated, batteries-included toolset for efficient Redux development. It is intended to be the standard way to write Redux logic.

It includes several utility functions that simplify the most common Redux use cases, including store setup, defining reducers, immutable update logic, and even creating entire "slices" of state at once without writing any action creators or action types by hand. It also includes the most widely used Redux addons, like Redux Thunk for async logic and Reselect for writing selector functions, so that you can use them right away.

The Redux core library is deliberately unopinionated. It lets you decide how you want to handle everything, like store setup, what your state contains, and how you want to build your reducers.

This is good in some cases, because it gives you flexibility, but that flexibility isn't always needed. Sometimes we just want the simplest possible way to get started, with some good default behavior out of the box. Or, maybe you're writing a larger application and finding yourself writing some similar code, and you'd like to cut down on how much of that code you have to write by hand.

#### Why You Should Use Redux Toolkit

Redux Toolkit makes it easier to write good Redux applications and speeds up development, by baking in our recommended best practices, providing good default behaviors, catching mistakes, and allowing you to write simpler code. Redux Toolkit is beneficial to all Redux users regardless of skill level or experience. It can be added at the start of a new project, or used as part of an incremental migration in an existing project.

Note that you are not required to use Redux Toolkit to use Redux. There are many existing applications that use other Redux wrapper libraries, or write all Redux logic "by hand", and if you still prefer to use a different approach, go ahead!

However, we strongly recommend using Redux Toolkit for all Redux apps.

Overall, whether you're a brand new Redux user setting up your first project, or an experienced user who wants to simplify an existing application, using Redux Toolkit will make your code better and more maintainable.

### MobX

MobX is a simple, scalable, boilerplate-free state management solution. It allows you to manage application state outside of any UI framework, making the code decoupled, portable and, above all, easy to test. It implements observable values, which are essentially using the publish/subscribe pattern. They differ in that the subscriptions are handled automatically. The engine tracks where you used the observables and only re-executes the side effects, like a render, if they change.

State is the heart of each application and there is no quicker way to create buggy, unmanageable applications than by producing an inconsistent state or state that is out-of-sync with local variables that linger around. Hence many state management solutions try to restrict the ways in which you can modify state, for example by making state immutable. But this introduces new problems; data needs to be normalized, referential integrity can no longer be guaranteed and it becomes next to impossible to use powerful concepts like classes in case you fancy those.

MobX makes state management simple again by addressing the root issue: it makes it impossible to produce an inconsistent state. The strategy to achieve that is simple: Make sure that everything that can be derived from the application state, will be derived. Automatically.

Conceptually MobX treats your application like a spreadsheet.

### The HookState

As its name suggests, Hookstate is a fast and flexible state management tool based on the React state Hook. It's a small library packed with features that include both global and local states, as well as partial state updates and asynchronously loaded states.

It is easy to use, very fast, full of features such as: global states, local states, asynchronously loaded states.

Those are some of the benifits of using the HookState tool.
