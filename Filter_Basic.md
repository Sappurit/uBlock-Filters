## Filters

- Network Filters (Simple blocking rules)
- Cosmetic Filters (Hiding elements)
  - Type
    - Generic = Apply to all domains
    - Specific = Prefixed with the domain on which they are meant to apply
  - Method
    - Standard Cosmetic Filters = CSS Selector
    - Procedural Cosmetic Filters = Javascript code is used to find DOM elements
```
Generic  -> Bad       ##body > div:has-text(Sponsored)
Specific -> Good      example.com##body > div:has-text(Sponsored)
```


## CSS Selectors

[https://www.w3.org/TR/selectors-3/#selectors](https://www.w3.org/TR/selectors-3/#selectors)  
[https://adblockplus.org/filter-cheatsheet](https://adblockplus.org/filter-cheatsheet)

- `example.com###advert` matches the element with the unique id "advert"
- `example.com##.advert` matches elements with the class "advert"
- `example.com##div[title^="adv"]` matches all \<div\> elements with title attribute starting with "adv"
- `example.com##div[title*="ver"]` matches all \<div\> elements with title attribute containing the string "ver"
- `example.com##div[title$="ert"]` matches all \<div\> elements with title attribute ending with "ert"
- `example.com##div[title~="advert"]` matches all \<div\> elements with title attribute "advert" in a list of whitespace-separated values
- `example.com##div[width="80%"][size="7"]` matches multiple conditions


## Extended CSS selectors (uBlock Origin Specific)

[https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters)

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


## CSS Combinators

- Decendant Selector (whitespace) = Any child, any level
- Child Combinator (>) = Direct child, first level only
- Adjacent Sibling Combinator (+) = Next younger sibling only, same level, same parent
- Following Sibling Combinator (~) = Any younger slibling, same level,  same parent


## How Element will be Selected

- `example.com##table > tr > td:has-text(Sponsored)` Only \<td\> will be selected
- `example.com##table:has(> tr > td:has-text(Sponsored))` Full \<table\> will be selected
