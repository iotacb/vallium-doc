# Navbar

The navbar component is a simple navbar component that can be used to navigate between pages.

View source code [here]().

## Basic usage

```jsx
import { Navbar } from "vallium";

function App() {
	return <Navbar>Button</Navbar>;
}
```

## Example

```jsx
import { Navbar } from "vallium";

function App() {
	return (
		<>
			<Navbar>
				<h1>
					Vallium
				</h1>
				<div>
					<a href="#">Home</a>
					<a href="#">About</a>
					<a href="#">Contact</a>
				</div>
			</Navbar>
		</>
	);
}
```

<!-- ![Centered rectangle window](../images/rect_window.png) -->

## Props

```ts
children: ReactNode; // The content of the navbar
```

## Used utilities

- [Breakpoints]()