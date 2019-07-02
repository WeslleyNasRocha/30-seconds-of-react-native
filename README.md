![Logo](/logo.png)

# 30 seconds of React-Native

> Curated collection of useful React snippets that you can understand in 30 seconds or less.

- Use <kbd>Ctrl</kbd> + <kbd>F</kbd> or <kbd>command</kbd> + <kbd>F</kbd> to search for a snippet.
- Contributions welcome, please read the [contribution guide](CONTRIBUTING.md).
- Snippets are written in **React 16.8.3**, **React-Native 0.59.9**, using **hooks**.

**NOTE**: This repo has no affiliation with the original [30 Seconds of Code](https://github.com/30-seconds/30-seconds-of-code), was based on [30 Seconds of React](https://github.com/30-seconds/30-seconds-of-react) but has no affiliation with it whatsoever

### Prerequisites

To import a snippet into your project, you must import `React` and copy-paste the component's JavaScript code like this:

```js
import React from 'react';

function MyComponent(props) {
  /* ... */
}
```

If there is any Style related to your component, copy-paste it to a new file with the same name and the appropriate extension, then import it like this:

```js
import './MyComponentStyle';
```

#### Related projects

- [30 Seconds of Code](https://30secondsofcode.org)
- [30 Seconds of CSS](https://30-seconds.github.io/30-seconds-of-css/)
- [30 Seconds of Interviews](https://30secondsofinterviews.org/)
- [30 Seconds of React](https://github.com/30-seconds/30-seconds-of-react)

## Table of Contents


### Visual

<details>
<summary>View contents</summary>

* [Ticker](#ticker)
</details>


---

## Visual
### Ticker

Renders a ticker component.

- Use the `React.useState()` hook to initialize the `ticker` state variable to `0`.
- Define two methods, `tick` and `reset`, that will periodically increment `timer` based on `interval` and reset `interval` respectively.
- Return a `<View>` with two `<Button>` elements, each of which calls `tick` and `reset` respectively.

```jsx
function Ticker(props) {
  const [ticker, setTicker] = React.useState(0);
  let interval = null;

  const tick = () => {
    reset();
    interval = setInterval(() => {
      if (ticker < props.times) setTicker(ticker + 1);
      else clearInterval(interval);
    }, props.interval);
  };

  const reset = () => {
    setTicker(0);
    clearInterval(interval);
  };

  return (
    <View>
      <Text style={{ fontSize: 100 }}>{ticker}</Text>
      <Button onPress={tick} title="Tick!" />
      <Button onPress={reset} title="Reset!" />
    </View>
  );
}
```

<details>
<summary>Examples</summary>

```jsx
<Ticker times={5} interval={1000} />
```
</details>

<br>[⬆ Back to top](#table-of-contents)


---

_This repository is a work in progress. If you want to contribute, please check the open issues to see where and how you can help out!_

_This README is built using [markdown-builder](https://github.com/30-seconds/markdown-builder)._

