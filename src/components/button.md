# Button

The button component is used to trigger an action or event, such as submitting a form, opening a dialog, canceling an action, or performing a delete operation.

View source code [here]().

## Basic usage

```jsx
import { Button } from "vallium";

function App() {
	return <Button>Button</Button>;
}
```

## Example usage

```jsx
import { useState } from "react"; 
import { Button } from "vallium";

function App() {
	const [count, setCount] = useState(0);
	return <>
		<Button onClick={() => setCount(count + 1)}>Click me</Button>
		<p>You clicked {count} times</p>
	</>
}
```

## Variants

```jsx
import { Button } from "vallium";

function App() {
	return (
		<>
			<Button variant="primary">Primary</Button>
			<Button variant="ghost">Ghost</Button>
			<Button variant="danger">Danger</Button>
		</>
	);
}
```

## Roundness

```jsx
import { Button } from "vallium";

function App() {
	return (
		<>
			<Button roundness="pill">Pill</Button>
			<Button roundness={10}>10px</Button>
			<Button roundness={20}>20px</Button>
			<Button roundness={30}>30px</Button>
		</>
	);
}
```

## Props

```ts
children: ReactNode; // The content of the button
```

```ts
className?: string; // Custom class names for the button
```

```ts
variant?: "primary" | "ghost" | "danger"; // The variant of the button
```

```ts
roundness?: "pill" | number; // The roundness of the button (in pixels)
```

## Used utilities

- [Variants]()