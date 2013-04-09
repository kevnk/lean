lean
====

Spend your time skinning a theme, not *re-skinning* a theme — Use this lightweight, responsive, mobile-first, boilerplate theme for eCommerce

### Objectives

1. A lean theme (inspired by [A List Apart](http://alistapart.com/article/improving-ux-through-front-end-performance)) (ultimately for a base Magento theme).
	- Mobile first and [dynamically add additional content if needed for larger screens](http://adactio.com/journal/5429/)
	- Use as few dom elements and classes as reasonable to start off with
2. A Blank base theme so you can spend your time skinning a theme, not *re-skinning* a theme
3. A Responsive theme (why do anything else anymore?)
4. Designer friendly 
	- Breakpoints before it breaks the design (as opposed to device specific breakpoints) [(Trent Walton's idea)](http://trentwalton.com/2013/02/07/where-to-start/).
	- Tell designers they have a range for each element so they can plan accordingly, instead of making a new comp for every single breakpoint (see "Responsive Setup and Thought Process" for more on this).
	- Uses [picturefill](https://github.com/scottjehl/picturefill) for images; offers you the greatest flexibility from a design standpoint, supports all browsers, no server side scripts, will work with cdn

##### Other Features
- Uses rems for font-sizes [(not my idea)](http://snook.ca/archives/html_and_css/font-size-with-rem)
- Uses baseline grid for vertical alignment of text [(A List Apart's idea)](http://alistapart.com/article/settingtypeontheweb)
- Uses JS library fallbacks [(a good idea)](http://www.1stwebdesigner.com/design/snippets-html5-boilerplate/)
- Uses SASS (Requires v3.2)

### Responsive Setup and Thought Process

This responsive design accounts for 4 layouts across widths from 320 - 1200. It is set up to be the easiest for the designer — which in turn will makes easier on you! Each column in the 1 column, 2 column, and 3 column layouts is designed to work within a certain range of width.

See the table below:

| layout | column class | min width | max width | final width (@media >1200px) |
|:-------|:-------------|:----------|:----------|:------------|
| 3 column | .col-left, .col-right | 150 | 320 | 205 |
|  | .col-main | 420 - | 720 | 720 |
| 2 column | .col-left, .col-right | 200 | 320 | 310 |
|  | .col-main | 420 - | 840 | 840 |
| 1 column | .col-main | 420 - | 1170 | 1170 |

The sidebars are able to stay within a certain range (and not get crazy wide) by splitting them in half (e.g. .left-top and .left-bottom) and distributing them accordingly. So for example, when the browser/device width is at 800px, the 3 column layout has the main content (.col-main) all across the top, and 4 columns under it (.left-top, .left-bottom, .right-top, .right-bottom in order of left to right). When you hit 690px width, the left and right column come back to form 2 columns under the main content.
