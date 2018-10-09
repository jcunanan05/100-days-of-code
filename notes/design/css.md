# CSS Notes

Quick and dirty tips / notes in my journey in css

## Making resizable underlines

HTML

```html
<section class="section"><h1 class="title">Hello</h1></section>
```

CSS

```css
.section .title::after {
  display: block;
  position: static;
  bottom: 0;
  width: 6rem;
  height: 0.3rem;
  background-color: $dark;
  content: "";
}
```

## Making 3d effect on buttons

1. Make a border shadow offset.
2. Add triangles on corners using pseudo elements `::before` and `::after`

[full example here](https://codepen.io/jcunanan05/pen/gBggWZ)
