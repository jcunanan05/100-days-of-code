 #100DaysOfCode Log - Round 3 - [Jonathan Albert Cunanan]

The log of my #100DaysOfCode challenge. Started on [July 13, 2017].

## Log

### R3D1   
* Took break. Watching Resilient CSS for now. Changed my perspective in using CSS for legacy browser support. (_feature queries_)

#### Notes from Resilient CSS

* Resources to look in browser support:
  * [caniuse.com](https://caniuse.com/)
  * MDN webdocs
  * Browser maker's support site

* Jen mentioned about HTML and CSS being _**Declarative language**_

* Also talked about error handling in different browsers - css properties that omitted by the older browsers. There are diff ways to handle errors and take advantage of it:
  * Checking if it looks good without that CSS property
  * Using overrides
  * Using feature queries - with fallback code, for those who use **reader mode** (strips of all css), and for those who don't support certain css properties.
  * In feature queries don't use ```@supports not`` for now - not all know feature queries so when you put a supported css property but the browser doesn't know feature queries, it will be ignored

* She also teached about tips on when using feature queries. 
  * CSS properties that is older than feature queries itself (like flexbox) won't run inside feature queries

* Failing Excellently 
  * thinking about some css properties that can achieve same results

Great series!!!

* Watched also LayoutLand's CSS Grid series

#### Notes from LayoutLand CSS Grid 
1. st Vid
  * Some terms to start: 
    * grid container
    * tracks (columns or rows)
    * grid items
    * grid cell
    * grid area
    * grid gap
    * line numbers
    * explicit vs implicit grid

2. nd vid
  * ```img``` by default is inline
  * Difference of ```auto-fit``` and ```auto-fill``` - auto-fill puts another tracks even when there's nothing to put there while auto fit doesn't