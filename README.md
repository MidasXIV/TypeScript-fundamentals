<p>
  <h2 align="center">Configure TypeScript with Webpack</h2>
</p>

***

### STEP 0: Init Project

```
mkdir "project-name" && cd "project-name" && npm init -y
```

### STEP 2: Configure TypeScript Environment

```
npx tsc --init --rootDir src --outDir build \
--esModuleInterop --resolveJsonModule --lib es6 \
--module commonjs --allowJs true --noImplicitAny true
```

| Option  | Description |
| :------ | :---------- |
| rootDir | This is where TypeScript looks for our code. We've configured it to look in the src/ folder. That's where we'll write our TypeScript. |
| outDir | Where TypeScript puts our compiled code. We want it to go to a build/ folder. |
| esModuleInterop | If you were in the JavaScript space over the past couple of years, you might have recognized that modules systems had gotten a little bit out of control (AMD, SystemJS, ES Modules, etc). For a topic that requires a much longer discussion, if we're using commonjs as our module system (for Node apps, you should be), then we need this to be set to true. |
| resolveJsonModule | If we use JSON in this project, this option allows TypeScript to use it. |
| lib | This option adds ambient types to our project, allowing us to rely on features from different Ecmascript versions, testing libraries, and even the browser DOM api. We'd like to utilize some es6 language features. This all gets compiled down to es5. |
| module | commonjs is the standard Node module system in 2019. Let's use that. |
| allowJs | If you're converting an old JavaScript project to TypeScript, this option will allow you to include .js files among .ts ones. |
| noImplicitAny | In TypeScript files, don't allow a type to be unexplicitly specified. Every type needs to either have a specific type or be explicitly declared any. No implicit anys. |

### STEP 4: Install Webpack and Webpack Cli

```
npm install webpack webpack-cli
```