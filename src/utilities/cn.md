# CN

This utility allows you to combine multiple class names into one.
This is extremely useful when you are using [Tailwind CSS]().

It uses [clsx]() and [twMerge]() under the hood.

View source code [here]().

## Basic usage

```jsx
import { cn } from "vallium";

type Props = {
    className?: string;
}

return Button({className}: Props) {
    return (<button className={cn(className, "py-4", "border-red border-2", "main-button")}>
    </button>)
}
```

## Props

```ts
...inputs: ClassValue[]; // Different classes to combine
```