# selector-attribute-operator-whitelist

**_Deprecated: Instead use the [`selector-attribute-operator-allowed-list`](https://github.com/stylelint/stylelint/tree/13.13.1/lib/rules/selector-attribute-operator-allowed-list/README.md) rule._**

Specify a list of allowed attribute operators.

<!-- prettier-ignore -->
```css
[target="_blank"] {}
/**    ↑
 * This operator */
```

## Options

`array|string`: `["array", "of", "operators"]|"operator"`

Given:

```
["=", "|="]
```

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
[class*="test"] {}
```

<!-- prettier-ignore -->
```css
[title~="flower"] {}
```

<!-- prettier-ignore -->
```css
[class^="top"] {}
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
[target] {}
```

<!-- prettier-ignore -->
```css
[target="_blank"] {}
```

<!-- prettier-ignore -->
```css
[class|="top"] {}
```
