# media-feature-name-blacklist

**_Deprecated: Instead use the [`media-feature-name-disallowed-list`](https://github.com/stylelint/stylelint/tree/13.13.1/lib/rules/media-feature-name-disallowed-list/README.md) rule._**

Specify a list of disallowed media feature names.

<!-- prettier-ignore -->
```css
@media (min-width: 700px) {}
/**     ↑
 * This media feature name */
```

## Options

`array|string|regex`: `["array", "of", "unprefixed", /media-features/ or "regex"]|"media-feature"|/regex/`

Given:

```
["max-width", "/^my-/"]
```

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
@media (max-width: 50em) {}
```

<!-- prettier-ignore -->
```css
@media (my-width: 50em) {}
```

<!-- prettier-ignore -->
```css
@media (max-width < 50em) {}
```

<!-- prettier-ignore -->
```css
@media (10em < my-height < 50em) {}
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
@media (min-width: 50em) {}
```

<!-- prettier-ignore -->
```css
@media print and (min-resolution: 300dpi) {}
```

<!-- prettier-ignore -->
```css
@media (min-width >= 50em) {}
```

<!-- prettier-ignore -->
```css
@media (10em < width < 50em) {}
```
