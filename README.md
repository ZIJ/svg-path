## SvgPath
[![NPM version](https://badge.fury.io/js/path-svg.png)](http://badge.fury.io/js/path-svg)
##### Chainable SVG path string generator with some sugar added

* Under 1kb minified and gzipped
* Supports Node, AMD and browser environments (EcmaScript 5 or newer, shims should also work)
* No dependencies

Writing SVG paths by hand is intuitively easy (see [W3 spec](http://www.w3.org/TR/SVG/paths.html#PathData)):
```html
<path class="SamplePath" d="M100,200 C100,100 250,100 250,200 S400,300 400,200" />
```

However, dynamic generation of path strings can be tricky and look ugly since most graphic algorithms utilize points, vectors and matrices, not just plain coordinates. That's where SvgPath can help:
```javascript
//start, control1, control2, middle are point objects with x and y properties
var path = SvgPath().to(start)
              .bezier3(control1, control2, middle)
              .bezier3(x1, y1, x2, y2).str();
```

Single-letter SVG methods are also supported (both absolute and relative):
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

## Changelog

#### 0.2.1

* Published as NPM module [path-svg](https://www.npmjs.org/package/path-svg)

#### 0.2.0

* Added point support
* Minor fixes

#### 0.1.1

* Fixed shortcut detection

#### 0.1.0

* Initial release

