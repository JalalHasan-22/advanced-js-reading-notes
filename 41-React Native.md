# Reading: React Native

React Native is an open source framework for building Android and iOS applications using React and the app platform’s native capabilities. With React Native, you use JavaScript to access your platform’s APIs as well as to describe the appearance and behavior of your UI using React components: bundles of reusable, nestable code. You can learn more about React in the next section. But first, let’s cover how components work in React Native.

### Views and mobile development

In Android and iOS development, a view is the basic building block of UI: a small rectangular element on the screen which can be used to display text, images, or respond to user input. Even the smallest visual elements of an app, like a line of text or a button, are kinds of views. Some kinds of views can contain other views. It’s views all the way down!

### Native Components

In Android development, you write views in Kotlin or Java; in iOS development, you use Swift or Objective-C. With React Native, you can invoke these views with JavaScript using React components. At runtime, React Native creates the corresponding Android and iOS views for those components. Because React Native components are backed by the same views as Android and iOS, React Native apps look, feel, and perform like any other apps. We call these platform-backed components <b>Native Components</b>.

React Native comes with a set of essential, ready-to-use Native Components you can use to start building your app today. These are React Native's Core Components.

React Native also lets you build your own Native Components for Android and iOS to suit your app’s unique needs. We also have a thriving ecosystem of these community-contributed components. Check out Native Directory to find what the community has been creating.

### Features and reasons to learn React-Native

1. Create native apps for Android and iOS using React
   React Native combines the best parts of native development with React, a best-in-class JavaScript library for building user interfaces.

Use a little—or a lot. You can use React Native today in your existing Android and iOS projects or you can create a whole new app from scratch.

2. Written in JavaScript—rendered with native code
   React primitives render to native platform UI, meaning your app uses the same native platform APIs other apps do.

Many platforms, one React. Create platform-specific versions of components so a single codebase can share code across platforms. With React Native, one team can maintain two platforms and share a common technology—React.

3. Seamless Cross-Platform
   React components wrap existing native code and interact with native APIs via React’s declarative UI paradigm and JavaScript. This enables native app development for whole new teams of developers, and can let existing native teams work much faster.

4. Fast Refresh
   See your changes as soon as you save. With the power of JavaScript, React Native lets you iterate at lightning speed. No more waiting for native builds to finish. Save, see, repeat.

## Expo

Expo is an open-source toolkit and platform that allows you to build a mobile application from a single codebase and release it to Android, iOS and the web simultaneously. We have been working with Expo recently, so we can share some observations and tips to give you a head start on your next mobile development project.

### Expo offers a strong development workflow

If you are a developer who likes seamless workflows, you will really appreciate the ability to start Expo and test the code with a browser when developing for mobile. It allows you to get an app up and running and start iterating on the code within seconds. You can view the content with a web browser, and you don’t need to install the Android or iOS development environments initially.

#### Some quirks

The browser automatically refreshes the page when an update is made to the code, which means you lose the screen you were working on. Because of the refresh, you may want to use React Router to ensure that you do not lose the screen you are working on. However, the Expo app replaces the new components seamlessly without any need to navigate back to the screen you were developing.

Some have found the Expo app to be buggy, forcing shutdown and restart on both the running app and the Expo app.

### Every Expo component uses Flexbox

Surprisingly, all components use Flexbox by default. Flexbox makes it much easier to organise UI components than the old methods of positioning components with absolute, float and other CSS attributes.

One of the main differences with web is that the default flex-direction in mobile is column rather than row. With most people holding their phone in portrait mode most of the time, this makes sense.

### React-native styles are not CSS

Although most style attributes are familiar, there are small differences between react-native and regular CSS when it comes to styling. The two main differences I noticed were:

1. React-native stylesheets do not cascade.
2. There are no pseudo elements, selectors or CSS animations.

### Testing must be done on your target platform

To be certain that your Expo code will work on your target platform, you need to test it on that platform. Even if your code works in a browser, it may not start in native. Browsers are more forgiving about what can be accepted. Some CSS and components will behave differently, and some code may not run on mobile.

This may be problematic for a developer whose main testing platform is the browser because you must always do final checks on the Expo app with an actual phone. Irrespective of the platform you are using, you will need to test thoroughly for runtime errors and inconsistencies on ALL target platforms before releasing your app.

### Expo’s limitations are resolvable

Expo offers many benefits, but if you want to use Expo for “standard” applications, you need to be aware of two limitations that will restrict the kind of application you can build:

1. Expo’s managed workflow does not support native components in the same way that react-native does.
   Expo’s default ‘Managed’ workflow is akin to create-react-app. This means that, unless a JS module is provided by Expo, you may miss out on Android and/or iOS functionalities. In practice, it generally means that you must accept the lowest common denominator for all three platforms (Web, Android and iOS), as well as the modules already provided by Expo. The solution is to use Expo with the Bare Workflow. In this way, you can avail of the full capabilities of native development.
2. Expo’s ecosystem is not as rich as React or mobile native.
   This is also true for react-native with regards to React. Expo is based on react-native, so it also it comes with the limits of react-native. React-native is younger than React with a smaller community. This is completely understandable because the library must support many platforms with little standardisation between them and maintaining expo packages is quite resource intensive.
   However, Expo supports forking code for each platform, so its limitations can be mitigated: You can choose to write code that is specific to a platform, such as iOS or web, simply by appending the platform name to a file. For example, you can write a module.ios.js that will be specific to iOS devices. Of course, the same can be done programmatically by detecting the current platform that the code is running on.
