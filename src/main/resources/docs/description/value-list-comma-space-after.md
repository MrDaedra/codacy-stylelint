# value-list-comma-space-after

Require a single space or disallow whitespace after the commas of value lists.

<!-- prettier-ignore -->
```css
a { background-size: 0, 0; }
/**                   ↑
 * The space after this comma */
```

The [`fix` option](https://github.com/stylelint/stylelint/tree/13.13.1/docs/user-guide/usage/options.md#fix) can automatically fix most of the problems reported by this rule.

## Options

`string`: `"always"|"never"|"always-single-line"|"never-single-line"`

### `"always"`

There _must always_ be a single space after the commas.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0,0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      , 0; }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0, 0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      , 0; }
```

### `"never"`

There _must never_ be whitespace after the commas.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0, 0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0 ,
      0; }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0,0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      ,0; }
```

### `"always-single-line"`

There _must always_ be a single space after the commas in single-line value lists.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0,0; }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0, 0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
    , 0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      ,0; }
```

### `"never-single-line"`

There _must never_ be whitespace after the commas in single-line value lists.

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0, 0; }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { background-size: 0,0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      ,0; }
```

<!-- prettier-ignore -->
```css
a { background-size: 0
      , 0; }
```
