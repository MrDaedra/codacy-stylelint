# function-url-scheme-whitelist

**_Deprecated: Instead use the [`function-url-scheme-allowed-list`](https://github.com/stylelint/stylelint/tree/13.13.1/lib/rules/function-url-scheme-allowed-list/README.md) rule._**

Specify a list of allowed URL schemes.

<!-- prettier-ignore -->
```css
a { background-image: url('http://www.example.com/file.jpg'); }
/**                        ↑
 *           This URL scheme */
```

A [URL scheme](https://url.spec.whatwg.org/#syntax-url-scheme) consists of alphanumeric, `+`, `-`, and `.` characters. It can appear at the start of a URL and is followed by `:`.

This rule ignores:

- URL arguments without an existing URL scheme
- URL arguments with variables or variable interpolation (`$sass`, `@less`, `--custom-property`, `#{$var}`, `@{var}`, `$(var)`)

## Options

`array|string|regex`: `["array", "of", /schemes/ or "/regex/"]|"scheme"|/regex/`

Given:

```
["data", "/^http/"]
```

The following patterns are considered violations:

<!-- prettier-ignore -->
```css
a { background-image: url('file://file.jpg'); }
```

The following patterns are _not_ considered violations:

<!-- prettier-ignore -->
```css
a { background-image: url('example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('/example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('//example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('./path/to/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('http://www.example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('https://www.example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('HTTPS://www.example.com/file.jpg'); }
```

<!-- prettier-ignore -->
```css
a { background-image: url('data:image/gif;base64,R0lGODlhAQABAIAAAAUEBAAAACwAAAAAAQABAAACAkQBADs='); }
```
