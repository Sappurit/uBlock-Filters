## Filters

- Network Filters
- Cosmetic Filters
  - Standard Cosmetic Filters = CSS Selector
  - Procedural Cosmetic Filters = Javascript code is used to find DOM elements
    - Generic = Apply to all domains.
    - Specific = Prefixed with the domain on which they are meant to apply.
```
Specific -> valid    example.com##body > div:has-text(Sponsored)
Generic  -> ignore   ##body > div:has-text(Sponsored)
```

## Cosmetic Filter Operators

- subject:not()
- subject:has()
- subject:has-text()
- subject:matches-css()
- subject:matches-css-before()
- subject:matches-css-after()
- subject:min-text-length()
- subject:upward()
- subject:watch-attr()
- subject:xpath()
