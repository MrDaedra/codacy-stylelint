# at-rule-whitelist

**_Deprecated: Instead use the [`at-rule-allowed-list`](https://github.com/stylelint/stylelint/tree/13.13.1/lib/rules/at-rule-allowed-list/README.md) rule._**

Specify a list of allowed at-rules.

<!-- prettier-ignore -->
```css
    @keyframes name {}
/** ↑
 * At-rules like this */
```

## Options

`array|string`: `["array", "of", "unprefixed", "at-rules"]|"at-rule"`

Given:

```
["extend", "keyframes"]
```

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
@import "path/to/file.css";
```

<!-- prettier-ignore -->
```css
@media screen and (max-width: 1024px) {
  a { display: none; }
}
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { @extend placeholder; }
```

<!-- prettier-ignore -->
```css
@keyframes name {
  from { top: 10px; }
  to { top: 20px; }
}
```

<!-- prettier-ignore -->
```css
@KEYFRAMES name {
  from { top: 10px; }
  to { top: 20px; }
}
```

<!-- prettier-ignore -->
```css
@-moz-keyframes name {
  from { top: 10px; }
  to { top: 20px; }
}
```