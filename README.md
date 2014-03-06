## SvgPath

##### Chainable SVG path string generator with some sugar added

* Under 1kb minified and gzipped
* Supports Node, AMD and browser environments (EcmaScript 5 or newer, shims should also work)
* No dependencies

Writing SVG paths by hand is intuitively easy:
```html
<path class="SamplePath" d="M100,200 C100,100 250,100 250,200 S400,300 400,200" />
```

However, dynamic generation of path strings can be tricky and look ugly. That's where SvgPath can help:
```javascript
var path = SvgPath().to(100, 200)
              .bezier3(100, 100, 250, 100, 250, 200)
              .bezier3(400, 300, 400, 200).str();
```

Single-letter methods are also supported (both absolute and relative):
```javascript
var path = SvgPath().M(100, 200)
              .C(100, 100, 250, 100, 250, 200)
              .S(400, 300, 400, 200).str();
```

Relative and absolute modes for convenience methods:

```javascript
var absolute = SvgPath().to(1000, 1000).hline(1010).vline(1010).hline(1000).close();
var relative = SvgPath().to(1000, 1000).rel().hline(10).vline(10).hline(-10).close();
```

Read more about SVG paths in [W3 spec](http://www.w3.org/TR/SVG/paths.html#PathData)
