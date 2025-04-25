<p align="center">
  <a href="https://www.npmjs.com/package/@zeytal/grid">
    <h2 align="center">@zeytal/grid</h2>
  </a>
</p>

<p align="center">
  A Zeytal utility package made by Hyperstonk.
</p>
<br/>

> This repository is dedicated to handling issues, feature requests, and discussions related to the @zeytal/grid package. The source code for this package is maintained elsewhere in a private repository.

## Install

```bash
pnpm add @zeytal/grid
```

```bash
yarn add @zeytal/grid
```

```bash
npm i @zeytal/grid
```

## Usage

```tsx
// Next.js RootLayout example.

import { isProdEnv } from "@/utils/isProdEnv";
import { GridOverlay } from "@zeytal/grid";

type Props = Readonly<{
  children: React.ReactNode;
}>;

export default function RootLayout({ children }: Props) {
  return (
    <html lang="en">
      <body>
        {children}
        {!isProdEnv() && <GridOverlay active={false} />}
      </body>
    </html>
  );
}
```

## Component props

### `breakpoints`

```tsx
import type { Breakpoints } from "@zeytal/grid";

import { GridOverlay } from "@zeytal/grid";

export default function ExampleComponent({ children }: Props) {
  // Define your breakpoints, their columns number and gutter size.
  const breakpoints: Breakpoints = {
    "0x": {
      columns: 2,
      gutter: 0,
    },
    "320x": {
      columns: 4,
      gutter: 16,
    },

    // ...

    "1920x": {
      columns: 16,
      gutter: 32,
    },
  };

  // Pass them to the breakpoints prop.
  return <GridOverlay breakpoints={breakpoints} />;
}
```

```ts
// Default breakpoints values:
{
  "0x": {
    columns: 24,
    gutter: 0,
  },
  "320x": {
    columns: 24,
    gutter: 0,
  },
  "400x": {
    columns: 24,
    gutter: 0,
  },
  "480x": {
    columns: 24,
    gutter: 0,
  },
  "576x": {
    columns: 24,
    gutter: 0,
  },
  "672x": {
    columns: 24,
    gutter: 0,
  },
  "768x": {
    columns: 24,
    gutter: 0,
  },
  "896x": {
    columns: 24,
    gutter: 0,
  },
  "1024x": {
    columns: 24,
    gutter: 0,
  },
  "1152x": {
    columns: 24,
    gutter: 0,
  },
  "1280x": {
    columns: 24,
    gutter: 0,
  },
  "1408x": {
    columns: 24,
    gutter: 0,
  },
  "1536x": {
    columns: 24,
    gutter: 0,
  },
  "1920x": {
    columns: 24,
    gutter: 0,
  },
};
```

### `active`

```tsx
import { GridOverlay } from "@zeytal/grid";

export default function ExampleComponent({ children }: Props) {
  // Decide whether or not your grid is displayed on load.
  // To toggle on/off the grid, hit the letter G on your keyboard.
  // Default value: true
  return <GridOverlay active={true} />;
}
```

### `maxWidth`

```tsx
import { GridOverlay } from "@zeytal/grid";

export default function ExampleComponent({ children }: Props) {
  // Two possible values: "last-breakpoint" | "none"
  // "last-breakpoint" — The grid stops growing when it hits your last defined breakpoint width.
  // "none" — The grid grows indefinitely.
  // Default value: "last-breakpoint"
  return <GridOverlay maxWidth="last-breakpoint" />;
}
```
