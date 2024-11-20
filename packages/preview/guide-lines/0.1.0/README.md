# The `guide-lines` Package

Show borders around the main text area, header and footer in Typst documents.

This may be useful to understand and debug layout issues.
The idea is similar to the LaTeX  [`layout`](https://ctan.org/pkg/layout)
package.

## Usage

```typst
#import "@preview/guide-lines:v0.1.0": background
#set page(paper: "a6")

#set page(background: background())
#lorem(100)

#pagebreak()

#set page(background: background(stroke: blue + 1pt))
#lorem(100)
```

![Output of the usage example, page 1](/docs/example-1-p1.svg) ![Output of the usage example, page 2](/docs/example-1-p2.svg)

## Known issues

The following limitations are known, PRs to address them are always welcome!:

- If `page.margin` contains the `inside` or `outside` keys, and `page.binding`
  is set to `auto`, the package will currently assume an LTR document with
  binding on the left side. It would be correct to follow Typst and determine
  the binding according to the text direction.

## Acknowledgements
The following Typst issues and forum post inspired this package and informed
its design and implementation:

- https://github.com/typst/typst/issues/5311
