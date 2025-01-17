---
sidebar_position: 1
title: Getting Started
---

import ThemedImage from "@theme/ThemedImage";
import useBaseUrl from "@docusaurus/useBaseUrl";
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# Getting Started

Before going through this tutorial, make sure that you have installed [Intutia's VS Code extension](https://marketplace.visualstudio.com/items?itemName=Intuita.intuita-vscode-extension).

If you don't have the extension installed, you just have to open the extensions menu in VS Code, search for Intuita, then click install.

---

There are two steps for easily running Intuita's codemods on your project.
1. Run Intuita
2. Compare Changes
3. Approve/Dismiss Changes

:::tip

If you like **videos** better, here is a quick [YouTube tutorial](https://youtu.be/pEGdu-cpu5k).

:::

### Step 1 -  Running Intuita
There are two ways you can run Intuita on your project.

#### Method 1 (Using package.json)
Open package.json in your project & applicable upgrade codemods automatically show up for you.

```jsx
"@mdx-js/react": "^1.6.22",
"clsx": "^1.2.1",
// highlight-next-line
"next": "12.3.1", //Hover over "next" for to execute codemods
"prism-react-renderer": "^1.3.5",
"react": "^17.0.2",
"react-dom": "^17.0.2"
```
<ThemedImage
  alt="Touca server signup page"
  sources={{
    light: useBaseUrl("img/intro/execute-next-codemods.png"),
    dark: useBaseUrl("img/intro/execute-next-codemods.png")
  }}
/>


#### Method 2 (Using the command menu)

1. Open VS Code's command menu (CMD/Ctrl + Shift + P).
2. Search for Intuita.
3. Run the codemods you want from the VS Code's Command menu & let Intuita transform your code automatically.

<ThemedImage
  alt="Touca server signup page"
  sources={{
    light: useBaseUrl("img/intro/execute-codemods.png"),
    dark: useBaseUrl("img/intro/execute-codemods.png")
  }}
/>


### Step 2 - Compare Changes
Quickly review, tweak, & apply the proposed changes one-by-one or in batches.

<Tabs>
<TabItem value="before-changes" label="Before Changes" default>

```jsx  title="Before Change"
import Link from 'next/link'
import styles from './NavBack.module.css'
import ArrowLeft from './images/arrow-left.svg'

export default function NavBack({ text, url }) {
  return (
    // red start
    <Link href={url}>
      <a className={styles.navBack}>
        // red end
        <img src={ArrowLeft} />
        {text}
        // red start
      </a>
    </Link>
  )
  // red end
}
```

</TabItem>

<TabItem value="after-changes" label="After Changes" default>

```jsx  title="After Change"
import Link from 'next/link'
import styles from './NavBack.module.css'
import ArrowLeft from './images/arrow-left.svg'

export default function NavBack({ text, url }) {
  return (
    // green start
    (<Link href={url} className={styles.navBack}>

    //green end

      <img src={ArrowLeft} />
      {text}
      // green start

    </Link>)
  );
  // green end
}
```

</TabItem>

</Tabs>

### Step 3 - Approve/Dismiss Changes

After comparing the changes made by Intuita, now you can look at each changes file and individually approve/dismiss the changed file.

Alternatively, you can approve all types of changes by clicking on the change type (the magic wand logo 🪄).

<ThemedImage
  alt="Touca server signup page"
  sources={{
    light: useBaseUrl("img/intro/approve-changes.png"),
    dark: useBaseUrl("img/intro/approve-changes.png")
  }}
/>



