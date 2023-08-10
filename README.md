# Setup

### How to setup a project with pnpm + Vite + React + Typescript + Tailwind CSS + postcss?

```console
pnpm create vite
# go through the propmpts like
# Project name: weather
# Select a framework: react
# Select a variant: typescript
```

In above example the directory called `weather` gets crated automatically.

```console
cd weather
pnpm install
pnpm run dev
```

At this point we have Dev server running with [[vite]] tooling.

Installing Tailwind CSS as a PostCSS plugin is the most seamless way to integrate it with build tools like webpack, Rollup, Vite, and Parcel.

```console
pnpm add tailwindcss postcss autoprefixer
pnpx tailwindcss init -p
```

Modify the `tailwind.config.js` file with below content

```js
module.exports = {
  content: ["./src/**/*.{js,jsx,ts,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

And the `index.css` file with,

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

`postcss.config.js` file should have all the plugins populated automatically and should looks like as,

```js
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```

At this point `pnpm run dev` should work with [[Tailwind CSS]].

Reference:

- [Tailwind CSS Docs](https://tailwindcss.com/docs/installation/using-postcss)
- [Larainfo](https://larainfo.com/blogs/install-setup-vite-react-typescript-tailwind-css-3)
