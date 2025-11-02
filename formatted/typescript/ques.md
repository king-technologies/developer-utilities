# Senior-level TypeScript interview questions

---

### **Core Type System**

1. Explain the difference between `unknown`, `any`, and `never`. When would you use each?

- `any`: Opts out of type checking. You can assign anything to/from `any`.
- `unknown`: Type-safe version of `any`. You can assign anything to `unknown`, but must narrow before using it.
- `never`: Represents values that never occur (e.g., a function that always throws or an exhaustive switch).

**Example:**

```ts
function fail(msg: string): never {
  throw new Error(msg);
}
let val: unknown = "x";
if (typeof val === "string") console.log(val.toUpperCase());
```

2. How does structural typing differ from nominal typing? Give a use case where structural typing causes subtle bugs.

TypeScript uses **structural typing** (duck typing): compatibility depends on structure, not declared type names.

**Example:**

```ts
interface Point {
  x: number;
  y: number;
}
interface Coord {
  x: number;
  y: number;
}
let p: Point = { x: 1, y: 2 };
let c: Coord = p; // allowed (same structure)
```

3. What are conditional types and how can they be used to infer return types dynamically?

Allow type selection based on compile-time checks.

**Syntax:**

```ts
T extends U ? X : Y
```

**Example:**

```ts
type ElementType<T> = T extends (infer U)[] ? U : T;
type A = ElementType<string[]>; // string
type B = ElementType<number>; // number
```

4. How do mapped types and template literal types help in building type-safe APIs?

Mapped types transform keys of a type. Template literal types combine string literal unions.

**Example:**

```ts
type ReadonlyProps<T> = { readonly [K in keyof T]: T[K] };
type EventHandlerNames<T extends string> = `on${Capitalize<T>}`;
type Events = EventHandlerNames<"click" | "hover">; // 'onClick' | 'onHover'
```

5. Explain type guards. How can you write custom type guards?
   Functions that narrow types during runtime.

**Example:**

```ts
function isString(x: unknown): x is string {
  return typeof x === "string";
}
function print(val: string | number) {
  if (isString(val)) console.log(val.toUpperCase());
}
```

6. What is type inference? How does TypeScript infer generic types in functions?

Compiler derives types from context or usage.

**Example:**

```ts
function identity<T>(arg: T) {
  return arg;
}
identity(5); // T inferred as number
```

7. Explain variance (covariance, contravariance, bivariance) in the context of TypeScript function types.

- **Covariant:** Output positions. `T` can be replaced by subtype.
- **Contravariant:** Input positions. Function parameters must accept supertypes.
- **Bivariant:** Functions in TS are partially bivariant for practicality.
- **Invariant:** No substitution.

**Example:**

```ts
type Fn<T> = (arg: T) => void;
let f: Fn<number> = (x) => {};
let g: Fn<any> = f; // allowed (bivariant), unsafe theoretically
```

8. What are discriminated unions? How do they improve type safety in switch statements?
   Tagged union types using a common literal field to narrow branches.

**Example:**

```ts
type Shape = { kind: "circle"; r: number } | { kind: "square"; s: number };
function area(s: Shape) {
  switch (s.kind) {
    case "circle":
      return Math.PI * s.r ** 2;
    case "square":
      return s.s ** 2;
  }
}
```

Compiler enforces exhaustiveness with `never` check.

9. How does TypeScript handle recursive types? Give an example.

Types that reference themselves. Used in JSON, trees, etc.

**Example:**

```ts
type Json = string | number | boolean | null | Json[] | { [k: string]: Json };
```

10. When does TypeScript widen a literal type, and how can you prevent it?
    Literal types (`'foo'`, `42`) are widened to `string`, `number` unless declared with `const`.

**Example:**

```ts
let x = "foo"; // type string
const y = "foo"; // type 'foo'
```

Use `as const` or explicit annotations to prevent widening.

---

### **Advanced Generics**

11. Explain how `keyof`, `typeof`, and indexed access types (`T[K]`) work together.

- `keyof T`: produces a union of property names.
- `typeof`: gets the type of a value or variable.
- `T[K]`: gets the type of a specific property.

**Example:**

```ts
const user = { id: 1, name: "Rohit" };
type User = typeof user; // { id: number; name: string }
type Keys = keyof User; // 'id' | 'name'
type IdType = User["id"]; // number
```

Used together to create generic utilities (e.g., `Pick`, `Omit`, `Record`).

11. What is Pick, Omit and Record in TypeScript? Provide examples of their usage.
    Pick, Omit, and Record are TypeScript utility types that transform object types.
    Each is generic and operates at the type level — no runtime effect.

`Pick`, `Omit`, and `Record` are **TypeScript utility types** that transform object types.
Each is generic and operates at the type level — no runtime effect.

---

### 1. `Pick<T, K>`

**Purpose:** Create a new type by selecting a subset of properties `K` from type `T`.

```ts
type User = {
  id: number;
  name: string;
  email: string;
};

type UserPreview = Pick<User, "id" | "name">;
// Result: { id: number; name: string }
```

**Use case:** When you only need a few fields from an existing type, such as for lightweight API responses.

---

### 2. `Omit<T, K>`

**Purpose:** Create a new type by removing properties `K` from type `T`.

```ts
type User = {
  id: number;
  name: string;
  email: string;
};

type UserWithoutEmail = Omit<User, "email">;
// Result: { id: number; name: string }
```

**Use case:** When you want to exclude certain fields (e.g., sensitive data before sending over a network).

---

### 3. `Record<K, T>`

**Purpose:** Create an object type with keys `K` and values of type `T`.

```ts
type Roles = "admin" | "user" | "guest";

type RolePermissions = Record<Roles, boolean>;
// Equivalent to: { admin: boolean; user: boolean; guest: boolean }

const permissions: RolePermissions = {
  admin: true,
  user: false,
  guest: false,
};
```

**Use case:** For mapping known keys to a consistent value type.

---

### Summary table

| Utility        | Input                    | Output                          | Common Use                  |
| -------------- | ------------------------ | ------------------------------- | --------------------------- |
| `Pick<T, K>`   | Object + keys to include | Subset of properties            | Extract specific fields     |
| `Omit<T, K>`   | Object + keys to exclude | Remaining properties            | Remove unwanted fields      |
| `Record<K, T>` | Keys + value type        | Object with uniform value types | Define dictionaries or maps |

---

**Composition example**

```ts
type User = { id: number; name: string; email: string; password: string };

type SafeUser = Omit<User, "password">;
type SafeUserPreview = Pick<SafeUser, "id" | "name">;
type SafeUserMap = Record<string, SafeUserPreview>;
```

Result:

```ts
// SafeUserMap is { [key: string]: { id: number; name: string } }
```

12. What are utility types like `Partial`, `Required`, `Pick`, and `Record` doing under the hood?

All are built on mapped and conditional types.

```ts
type Partial<T> = { [P in keyof T]?: T[P] };
type Required<T> = { [P in keyof T]-?: T[P] };
type Pick<T, K extends keyof T> = { [P in K]: T[P] };
type Record<K extends keyof any, T> = { [P in K]: T };
```

They transform property modifiers (`?`, `readonly`) and key sets at compile time.

13. Write a generic function that deeply makes all object properties readonly.

```ts
type DeepReadonly<T> = {
  readonly [K in keyof T]: T[K] extends object ? DeepReadonly<T[K]> : T[K];
};
```

Applies recursively, enforcing immutability in nested structures.

14. How can you constrain generic parameters to enforce relationships between them?
    You can link multiple generics.

**Example:**

```ts
function getProp<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

`K` depends on the keys of `T`, ensuring type-safe property access.

15. How would you implement your own version of `Omit<T, K>`?

```ts
type Omit<T, K extends keyof any> = Pick<T, Exclude<keyof T, K>>;
```

Removes specified keys from an object type.

---

### **Practical and Runtime Concerns**

16. What are the trade-offs of using decorators in TypeScript?
    Decorators add metadata or modify behavior at runtime.

**Pros:**

- Declarative dependency injection.
- Simplifies framework-level logic (e.g., NestJS).

**Cons:**

- Experimental, not part of ECMAScript standard.
- Metadata reflection adds runtime cost.
- Complicates testing and type inference.

17. How does TypeScript handle module resolution for CommonJS vs ES Modules?

- **CommonJS:** uses `require`, synchronous, runtime binding.
- **ESM:** uses `import/export`, static analysis, tree-shaking enabled.
  TypeScript uses `moduleResolution` config to choose algorithm:
- `node16` or `nodenext` for hybrid projects.
- Type differences mainly affect `default` import behavior.

18. How would you ensure runtime type safety when consuming dynamic data (e.g., JSON APIs)?
    TypeScript types vanish at compile time. Use runtime validators:

- Libraries: `zod`, `io-ts`, `runtypes`.
- Example:

```ts
import { z } from "zod";
const UserSchema = z.object({ id: z.number(), name: z.string() });
type User = z.infer<typeof UserSchema>;
```

`UserSchema.parse(data)` ensures runtime correctness.

19. Explain how TypeScript integrates with Babel and what gets stripped at compile time.

- Babel strips types but doesn’t perform type checking.
- Use `tsc --noEmit` for static analysis.
- Babel + TS allows faster builds but weaker type enforcement.

20. What are the implications of `emitDecoratorMetadata` and `reflect-metadata` in production?
    When `emitDecoratorMetadata` is enabled, TypeScript emits runtime type metadata for decorated members.

**Example:**

```ts
import "reflect-metadata";
@injectable()
class Service {
  constructor(@inject(UserRepo) repo: UserRepo) {}
}
```

**Implications:**

- Useful for DI frameworks (NestJS, Inversify).
- Increases bundle size and leaks design info—avoid in lightweight builds.

---

### **Architecture and Patterns**

### 21 — Designing a large-scale TypeScript monorepo with shared types and utilities

- Layout: split into packages under `/packages` (e.g. `api-types`, `ui`, `services`, `lib`, `cli`). Keep types in a dedicated package like `@org/schema` or `@org/types`.
- Tooling: use pnpm or yarn workspaces for fast installs. Use Turborepo or Nx for task orchestration and caching.
- Type sharing: publish internal packages or use workspace packages. Prefer **type-only** packages (no runtime) for shared interfaces and DTOs.
- Build: enable `composite: true` and `declaration: true` in `tsconfig.json` for package refs. Use `tsc --build` with project references for incremental builds.
- Path mapping: use workspace package names rather than deep `paths` where possible. If using `paths`, keep mappings in root `tsconfig.base.json`.
- Versioning: use independent versions for packages that change often. Use changefiles or semantic-release automation.
- CI/CD: build and type-check changed packages only. Run `tsc --build` and tests per affected package. Use strict lint and type checks in PR gates.
- Runtime contracts: separate runtime validators (zod/io-ts/ajv) into a package proxied from `@org/schema` so types and validators co-evolve.
- Testing: unit tests inside packages. Add integration tests in a top-level `e2e` package.
- Docs and onboarding: generate API docs from types or JSDoc. Document publishing and upgrade paths.
- Performance: prefer type-only exports, avoid huge union types in hot paths, enable `skipLibCheck` only when necessary.

Key principles:

- Use **project references** (`composite: true` in `tsconfig`).
- Separate shared packages (`@types`, `utils`) into isolated modules.
- Tools: Nx, Turborepo, or pnpm workspaces.
- Ensure type version alignment via root `tsconfig.base.json`.

### 22 — Pros and cons of TypeScript in microservices / micro-frontends

Pros

- Stronger contracts across teams. Types reduce runtime surprises.
- Better DX and IDE experience. Faster dev with autocompletion and refactor safety.
- Share types for DTOs, events, messages, and component props.
- Easier incremental migration from JS.

Cons

- Version skew risk. Different services using different type versions cause mismatch.
- Build complexity. Cross-repo type changes require coordinated releases or workspaces.
- Runtime validation still needed. Types vanish at runtime; you need validators for network boundaries.
- Bundle size concerns in micro-frontends if you accidentally ship heavy shared code.
- Operational coupling. Tight type contracts can slow independent deployments if not versioned.

Mitigations

- Version APIs and types semantically.
- Use codegen (OpenAPI, GraphQL) or stable published type packages.
- Keep runtime validators close to the types.
- Automate compatibility checks in CI.

### 23 — How TypeScript enforces contract-driven development between backend and frontend

Use TypeScript to define shared schemas:

- Generate API contracts via tools like **tRPC**, **OpenAPI + typegen**, or **GraphQL codegen**.
- Eliminates mismatch between client/server models.

**Example (tRPC):**

```ts
const appRouter = t.router({
  user: t.procedure.input(z.number()).query((id) => db.user.find(id)),
});
type AppRouter = typeof appRouter;
```

- Shared type packages. Publish `@org/api-types` and consume on frontend/backend so both compile against same DTOs.
- Code generation. Generate types from OpenAPI/GraphQL schemas so both sides derive the same contract.
- Runtime validators. Generate validators (zod/io-ts/ajv) alongside types to validate incoming/outgoing payloads.
- CI checks. Fail builds when consumers reference incompatible types or when type package changes are not accompanied by version bumps.
- End-to-end type tests. Use contract tests that serialize/deserialize sample payloads through both layers.
- Typed clients. Generate typed API clients so frontend call signatures match backend responses at compile time.
- API compatibility linting. Add automated checks that compare schema diffs and flag breaking changes.

### 24 — Safely refactoring a TypeScript codebase without breaking contracts

- Use **strict** mode (`strict: true` in tsconfig).
- Apply **noImplicitAny**, **noUnusedLocals**, **noUncheckedIndexedAccess**.
- Use automated refactors (`ts-morph`, `ts-prune`) and test coverage to confirm no contract breaks.
- Avoid `any` and use `unknown` where necessary for staged migrations.

- Start with tests. Ensure unit, integration, and contract tests pass.
- Use small incremental changes. Break big refactors into atomic PRs.
- Deprecation cycle. Mark old APIs deprecated, keep them for one release, add migration docs.
- Static checks. Use `tsc --noEmit` with strict flags and `eslint` rules in CI.
- Project references. Use `composite` builds to surface cross-package breakages early.
- Codemods. Automate repetitive renames with ts-morph or jscodeshift.
- Runtime safety. Keep validators in sync with types. Run sample payloads through validators.
- Versioning and compatibility tests. Publish and test new type package versions in a staging environment before rollout.
- Feature flags. For behavior changes, gate them behind flags and roll out gradually.
- Rollback plan. Keep a tested, fast rollback path for any release that breaks contracts.

### 25 — Leveraging advanced TypeScript features in NestJS and React

- NestJS

  - DTOs + `class-transformer` + `class-validator` for runtime validation plus static types.
  - Use generics in services and repositories for reusable patterns, e.g. `CrudService<T, CreateDto, UpdateDto>`.
  - Mapped types for partial/update DTOs: `PartialType(CreateDto)`.
  - Discriminated unions for polymorphic payloads and guards.
  - Project refs to share `@org/schema` between backend modules and microservices.

- React

  - Strongly typed hooks with generics: `useState<T>`, `useReducer<R, A>`.
  - Discriminated unions for component props to enforce exclusive variants.
  - Utility types for props manipulation: `Omit`, `Pick`, `ComponentProps<typeof Comp>`.
  - JSX typing: `FC<Props>` vs typed function components with `Props` generics to avoid implicit `children` issues.
  - Inference helpers: use `ReturnType`, `Parameters`, and conditional types to derive types for HOCs and factories.
  - Type-safe contexts: `createContext<T | undefined>` with helper `useCtx(): T` that throws if undefined.

```ts
function useFetch<T>(url: string): [T | null, boolean] { ... }
const [data, loading] = useFetch<User>("/api/user");
```

- Cross-cutting patterns

  - Use conditional and mapped types for derived DTOs (`Readonly`, `Required`, `Partial`).
  - Use `as const` plus literal types for strict enums and better narrowing.
  - Keep runtime validators generated from types or source schema to avoid drift.
  - Prefer `unknown` for external inputs and refine with type guards.

### **Q1. Write a function that makes all properties in an object deeply readonly.**

**Answer:**

```ts
type DeepReadonly<T> = {
  readonly [K in keyof T]: T[K] extends object ? DeepReadonly<T[K]> : T[K];
};
```

---

### **Q2. Implement a function that extracts only string properties from an object.**

**Answer:**

```ts
type StringProps<T> = {
  [K in keyof T as T[K] extends string ? K : never]: T[K];
};
```

---

### **Q3. Generic function to get a value by key safely.**

**Answer:**

```ts
function getValue<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

---

### **Q4. Create a utility type to replace certain keys’ types in an object.**

**Answer:**

```ts
type Replace<T, R> = Omit<T, keyof R> & R;
```

---

### **Q5. Implement type-safe event emitter.**

**Answer:**

```ts
type Events = {
  login: { user: string };
  logout: void;
};

class Emitter<T> {
  private listeners: { [K in keyof T]?: ((arg: T[K]) => void)[] } = {};
  on<K extends keyof T>(event: K, fn: (arg: T[K]) => void) {
    (this.listeners[event] ||= []).push(fn);
  }
  emit<K extends keyof T>(event: K, arg: T[K]) {
    this.listeners[event]?.forEach((fn) => fn(arg));
  }
}
```

### **1. DeepPartial**

**Goal:** Make all nested properties optional.

```ts
type DeepPartial<T> = {
  [K in keyof T]?: T[K] extends object ? DeepPartial<T[K]> : T[K];
};
```

**Usage:**

```ts
type A = { a: { b: { c: number } } };
type B = DeepPartial<A>; // { a?: { b?: { c?: number } } }
```

---

### **2. Extract function parameter types**

**Goal:** Infer parameter types from a function type.

```ts
type Params<T extends (...args: any[]) => any> = T extends (
  ...args: infer P
) => any
  ? P
  : never;
```

**Example:**

```ts
type Fn = (x: number, y: string) => void;
type P = Params<Fn>; // [number, string]
```

---

### **3. Enforce readonly for array contents**

**Goal:** Create a type that freezes array elements as well.

```ts
type DeepReadonlyArray<T> = ReadonlyArray<
  T extends object ? DeepReadonly<T> : T
>;
```

---

### **4. Typed EventEmitter**

**Goal:** Enforce strong typing for event registration and emission.

```ts
type Events = { start: string; stop: number };

class TypedEmitter<T> {
  private handlers: { [K in keyof T]?: ((arg: T[K]) => void)[] } = {};
  on<K extends keyof T>(event: K, fn: (arg: T[K]) => void) {
    (this.handlers[event] ||= []).push(fn);
  }
  emit<K extends keyof T>(event: K, arg: T[K]) {
    this.handlers[event]?.forEach((fn) => fn(arg));
  }
}
```

---

### **5. Tuple to Object**

**Goal:** Convert tuple of keys to an object with same key/value pairs.

```ts
type TupleToObject<T extends readonly string[]> = {
  [K in T[number]]: K;
};
```

**Example:**

```ts
type T = TupleToObject<["a", "b"]>; // { a: 'a'; b: 'b' }
```

---

### **6. Flatten nested object keys**

**Goal:** Convert `{a:{b:number}}` → `{"a.b": number}`.

```ts
type Flatten<T, P extends string = ""> = {
  [K in keyof T & string as T[K] extends object
    ? never
    : P extends ""
    ? K
    : `${P}.${K}`]: T[K];
} & {
  [K in keyof T & string as T[K] extends object
    ? `${P extends "" ? K : `${P}.${K}`}`
    : never]: Flatten<T[K], `${P extends "" ? K : `${P}.${K}`}`>;
}[keyof T & string];
```

---

### **7. Enforce immutability at runtime**

**Goal:** Deep-freeze an object using TS type + runtime.

```ts
function deepFreeze<T>(obj: T): Readonly<T> {
  Object.freeze(obj);
  Object.getOwnPropertyNames(obj).forEach((name) => {
    const val = (obj as any)[name];
    if (typeof val === "object" && val !== null) deepFreeze(val);
  });
  return obj;
}
```

---

### **8. Create a conditional mapper**

**Goal:** Replace all string fields with number fields.

```ts
type ReplaceStrings<T> = {
  [K in keyof T]: T[K] extends string ? number : T[K];
};
```

**Example:**

```ts
type A = { name: string; age: number };
type B = ReplaceStrings<A>; // { name: number; age: number }
```

---

### **9. Validate API response type**

**Goal:** Write a function that fetches and validates API responses.

```ts
import { z } from "zod";
async function fetchTyped<T>(url: string, schema: z.ZodType<T>): Promise<T> {
  const res = await fetch(url);
  const json = await res.json();
  return schema.parse(json);
}
```

**Usage:**

```ts
const User = z.object({ id: z.number(), name: z.string() });
const user = await fetchTyped("/api/user", User);
```

---

### **10. Advanced utility: Union to Intersection**

**Goal:** Convert a union type into an intersection type.

```ts
type UnionToIntersection<U> = (U extends any ? (x: U) => void : never) extends (
  x: infer I
) => void
  ? I
  : never;
```

**Example:**

```ts
type U = { a: string } | { b: number };
type I = UnionToIntersection<U>; // { a: string } & { b: number }
```

---
