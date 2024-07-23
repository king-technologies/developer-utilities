# Svelte

## Introduction

- It's a JavaScript tool for building UI `<Components />`
- Svelte is a compiler that convert declarative components into imperative JavaScript code, as a result you get a smaller bundle size with higher performance
- Components are created using .svelte files which contains 3 parts: 
  - Script Tag for your JavaScript Code which can also be TypeScript code.
  - Style Tag for your CSS Styles and which can also you pre-processors like Scss, Less etc.
  - HTML Template Tag for your HTML markup with declarative syntax.

## Prerequisites

- Node 18+ installed
- A Code Editor like VS Code, or Zed

## Setup

- Open a terminal and run `npm create svelte@latest my-svelte-app` to create a new project.
- Choose a template, most of the time you are good with Skeleton Project.
- Then we will have option to Choose type checking, you should choose one option either Javascript with JSDoc comments or TypeScript.
  - If you know TypeScript, you can choose TypeScript otherwise JavaScript with JSDoc comments will also be good to have awesome type checking & autocomplete experience.
- Then you'll have option to choose multiple additional option like ESLint, Prettier, Playwright, Vitest. you can choose any of them according to your preference.
- Then open the project in your code editor.
- From Terminal you can run `npm i` or `npm install` to install all the dependencies.
- Then you can run `npm run dev` to start the development server.
- Then if everything is good, you'll be able to see the project running on `localhost:5173` most likely or you'll see a link in the terminal to open in the browser.


## DevTools

- [Svelte for VS Code](https://marketplace.visualstudio.com/items?itemName=svelte.svelte-vscode) extension for VS Code to get the code formatting and autoformatting features. This also help us to generate boilerplate code for components and extract component easily