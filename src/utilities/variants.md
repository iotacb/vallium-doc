# Variants

This utility allows you to create variants for your components. It uses [styled-components]() under the hood, so you have to use styled-components to use this utility.

In future versions, this utility will support default styling properties, so you don't have to use styled-components.

Also there will be a similar utility when using [Tailwind CSS]().

View source code [here]().

## Basic usage

```jsx
import { variants } from "vallium";
import styled from "styled-components";

type Props = {
    variant?: "primary" | "secondary";
}

function Button({variant = "primary"}: Props) {
    const vars = variants(variant, {
        primary: {
            style: `
                background-color: blue;
                color: white;

                &:hover {
                    background-color: darkblue;
                }
            `
        },
        secondary: {
            style: `
                background-color: red;
                color: white;

                &:hover {
                    background-color: darkred;
                }
            `
        }
    });

    return <ButtonContainer variant={vars}>Button</ButtonContainer>;
}

const ButtonContainer = styled.button`
    ${(props) => props.variant}
`;
```

## Tips

You can enable syntax highlighting when installing the [vscode-styled-components]() (Or the extension for your favorite editor) extension.

Then you can add the `css` function from [styled-components]() to your code, so you can get syntax highlighting for your CSS.

```jsx
import { variants } from "vallium";
import styled, { css } from "styled-components";

type Props = {
    variant?: "primary" | "secondary";
}

function Button({variant = "primary"}: Props) {
    const vars = variants(variant, {
        primary: {
            style: css`
                background-color: blue;
                color: white;

                &:hover {
                    background-color: darkblue;
                }
            `
        },
        secondary: {
            style: css`
                background-color: red;
                color: white;

                &:hover {
                    background-color: darkred;
                }
            `
        }
    });

    return <ButtonContainer variant={vars}>Button</ButtonContainer>;
}

const ButtonContainer = styled.button`
    ${(props) => props.variant}
`;
```

You can add a global style to your variant by adding the style as the last argument to the `variants` function.

```jsx
import { variants } from "vallium";
import styled, { css } from "styled-components";

type Props = {
    variant?: "primary" | "secondary";
}

function Button({variant = "primary"}: Props) {
    const vars = variants(variant, {
        ...
    }, `
        border: none;
        padding: 10px 20px;
        border-radius: 5px;
    `);

    return <ButtonContainer variant={vars}>Button</ButtonContainer>;
}

const ButtonContainer = styled.button`
    ${(props) => props.variant}
`;
```

## Props

```ts
variant: string; // The current selected variant
```

```ts
variants: Variant; // The variants object in which you can define the styling for each variant
```

```ts
style?: string | FlattenSimpleInterpolation; // A style that will be added to all variants
```

## Used utilities

- [Variant](../misc/types.md#variant)