# My default FE template starter

Best practices for TailwindCSS:

```jsx
/* 1. Use object for classes and the comment for intelliSense */
const classes = {
  base: /*tw:*/ `bg-red-500`,
  colors: {
    blue: /*tw:*/ `text-blue-500`,
    yellow: /*tw:*/ `text-yellow-500`,
  },
}

/* 2. Avoid using CSS @apply with tw-merge */
// https://github.com/dcastil/tailwind-merge/discussions/122#discussioncomment-3369550
```

**Intellisense for CSS Modules:**
F1 -> TypeScript: Select TypeScript version -> Select Workspace

**Install the following extensions for better Developer Experience**

```
- Prettier - Code formatter
- Tailwind CSS IntelliSense
- ESLint
```

- Next.js 12 (React 18)
- TS v4.7
- TailwindCSS v3
- RadixUI
- RadixUI + Tailwind integration
- Tailwind merge
- Intelisense for CSS modules

```bash
# install deps
npm i
# run
npm run dev
```
