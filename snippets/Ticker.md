### Ticker

Renders a ticker component.

* Use the `React.useState()` hook to initialize the `ticker` state variable to `0`.
* Define two methods, `tick` and `reset`, that will periodically increment `timer` based on `interval` and reset `interval` respectively.
* Return a `<View>` with two `<Button>` elements, each of which calls `tick` and `reset` respectively.

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
      <Button onClick={tick}>Tick!</Button>
      <Button onClick={reset}>Reset</Button>
    </View>
  );
}
```

```jsx
<Ticker times={5} interval={1000} />
```

<!-- tags: visual,state -->

<!-- expertise: 1 -->
