# function-parentheses-space-inside

Require a single space or disallow whitespace on the inside of the parentheses of functions.

<!-- prettier-ignore -->
```css
a { transform: translate( 1, 1 ); }
/**                     ↑      ↑
 * The space inside these two parentheses */
```

The [`fix` option](https://github.com/stylelint/stylelint/tree/13.13.1/docs/user-guide/usage/options.md#fix) can automatically fix all of the problems reported by this rule.

## Options

`string`: `"always"|"never"|"always-single-line"|"never-single-line"`

### `"always"`

There _must always_ be a single space inside of the parentheses.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1); }
```

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1 ); }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate( 1, 1 ); }
```

### `"never"`

There _must never_ be whitespace on the inside of the parentheses.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate( 1, 1 ); }
```

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1 ); }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1); }
```

### `"always-single-line"`

There _must always_ be a single space inside the parentheses of single-line functions.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1) }
```

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1 ) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate( 1, 1 ) }
```

<!-- prettier-ignore -->
```css
a { transform: translate(1,
  1) }
```

<!-- prettier-ignore -->
```css
a {
  transform: translate(
    1,
    1
  )
}
```

### `"never-single-line"`

There _must never_ be whitespace inside the parentheses of single-line functions.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate( 1, 1 ) }
```

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1 ) }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { transform: translate(1, 1) }
```

<!-- prettier-ignore -->
```css
a { transform: translate( 1,
  1) }
```

<!-- prettier-ignore -->
```css
a {
  transform: translate(
    1,
    1
  )
}
```
