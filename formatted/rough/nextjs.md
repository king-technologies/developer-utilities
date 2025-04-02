# NextJS

- The React Framework for web applications.
- Full Stack React Framework.
- Server Side Rendering.
- Good SEO
- Server Side Components
- Navigation and Routing

```bash
npx create-next-app@latest my-next-app
```

### Files

- page.jsx - Page Component
- api.js - API Functions
- layout.jsx - Layout Component
- not-found.jsx - 404 Page
- loading.jsx - Loading Page
- error.jsx - Error Page

- Children is default prop for Layout Component, that is used to render the page component.

```jsx
export const metadata = {
  title: "Page Title",
  description: "Page Description",
  keywords: "Page Keywords",
};
```

- metadata is used to set the title, description and keywords for the page. aka metadata for the page.

- "@" is used to import the module from the root of the project. can be edited in the jsconfig.json file.

### Add Image

#### Import and Image Component

- Image is in src/image/banner.webp

```jsx
import banner from "@image/banner.webp";

<Image src={banner.src} alt="Banner" width={100} height={100} fill />;
```

#### Add Remote Image

- If adding any remote image, need to define the host & protocal in next.config.mjs file

```mjs
export default nextConfig = {
  images: {
    remotePatterns: [
      {
        host: "example.com",
        protocal: "https",
      },
    ],
  },
};
```

### Routing

- NextJS uses file based routing.

/course/course-details/[course-slug]\page.jsx <!-- need to check the syntax -->

```jsx
<Link
  href="/course/course-details/course-1"
>
  NextJS
</Link>
<Link
  href="/course/course-details/[course-slug]"
  as="/course/course-details/nextjs"
>
  NextJS
</Link>
```

- We can get this variable in the page component using useRouter hook.

```jsx
const router = useRouter();
const { courseSlug } = router.query;
```

or

```jsx
export default function page({ params }) {
  const { course-slug } = params;
}
```
