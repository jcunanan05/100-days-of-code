## HTML & CSS

Basically, before I started reading the front-end handbook, I am doing freecodecamp projects so I have an ample amount of HTML and CSS knowledge so I went straight to good HTML and CSS practices.

### Authoring CSS by codeguide

res: [http://codeguide.co/#css]()

#### Syntax

- Use 2 soft tabs (spaces)
- Grouped selectors in new line
- No spaces in `rgb()`, `rgba()`, `hsl()`, `hsla()`, `rect()`
- `-.5` instead of -0.5
- No units in `0`

```css
/* Good CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0, 0, 0, 0.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

#### Declaration order

1. Positioning
2. Box Model
3. Typographic
4. Visual

```css
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 100;

  /* Box-model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;

  /* Typography */
  font: normal 13px "Helvetica Neue", sans-serif;
  line-height: 1.5;
  color: #333;
  text-align: center;

  /* Visual */
  background-color: #f5f5f5;
  border: 1px solid #e5e5e5;
  border-radius: 3px;

  /* Misc */
  opacity: 1;
}
```
