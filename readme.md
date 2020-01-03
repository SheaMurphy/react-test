# react-query-test

An expressive testing library for React:

```js
import React, { useState } from "react";
import $ from "react-query-test";

const Counter = () => {
  const [counter, setCounter] = useState(0);
  const increment = () => setCounter(counter + 1);
  return <div onClick={increment}>{counter}</div>;
};

it("increments the counter one at a time", async () => {
  const $counter = $(<Counter />);
  expect($counter.html()).toEqual("<div>0</div>");
  await $counter.click();
  expect($counter.html()).toEqual("<div>1</div>");
  await $counter.click();
  expect($counter.html()).toEqual("<div>2</div>");
});
```

> This is a very early testing package, use at your own risk
