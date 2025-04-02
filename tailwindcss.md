# TailwindCSS

- VS Code Extension for TailwindCSS IntelliSense, Validation and Information about the classes.
- [TailwindCSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)
- [Headwind](https://marketplace.visualstudio.com/items?itemName=heybourn.headwind)

## Arbitrary Value

w-[30rem], w-[30cqw]
bg-[rgb(255,255,255)]
bg-[url(./assets/react.svg)]
[border-image:url(./assets/react.svg)]
[display:flex]

## Conditional Styling (clsx)

```jsx
clsx("p-4 text-4x1 w-96", active ? "bg-green-500" : "bg-red-500"); // Terinary Operator for conditional styling
clsx("p-4 text-4x1 w-96 bg-red-500", !active && "bg-green-500"); // Logical Operator for conditional styling
clsx(
  "p-4 text-4x1 w-96 bg-red-500",
  !active && "bg-green-500",
  !child && "text-red-500"
); // Multiple conditional styling
```

## CSS Vars and Arbitrary Calcs

```jsx
"[--container-gap:15px]"; // Single value
"[--container-gap:15px] lg:[--container-gap:30px]"; // Single breakpoint
"[--container-gap:15px] lg:[--container-gap:30px] 2xl:[--container-gap:60px]"; // Multiple breakpoints
"[--container-gap:15px] lg:[--container-gap:30px] 2xl:[--container-gap:60px] hover:[--container-gap:120px]"; // Hover
```

gap-[var(--container-gap)]
gap-[calc(var(--container-gap) * 2)]

```

```
