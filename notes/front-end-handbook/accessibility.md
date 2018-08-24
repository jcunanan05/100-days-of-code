## Accessibility

### 9 tips to get bare minimum of accessibility

res: [https://medium.com/@realabhijeet4u/9-tips-to-get-bare-minimum-of-web-accessibility-739899a9437c]()

1. Keyboard Accessible
  * Fix your markup and make sure interactive elements (_input, buttons, etc..._)
  * By default this is already implemented by the browser
  * `div` and `span` are omitted by default

2. Tab order
  * Arrange your markup in a Right To Left manner when the user uses tabs, it will be _right to left
  * Don't the tab selector jump places

3. tabindex
  * take advantage of `tabindex=0` to make non-interactive elements accessible
  * Positive `tabindex` is considered anti-pattern and confusing

4. Use native elements
  * Use `button` instead of making a div look like button

5. Check _WAI-ARIA_ guidelines for making your custom elements
  * link [https://www.w3.org/TR/wai-aria-practices-1.1/]()

6. Semantic tags and headings for screen readers
  * use `alt` for images
  * use proper headings
  * use semantic tags like `header`, `footer`, `main`, `section`, `nav`
  * in custom elements, use label or aria attributes

7. Use labels and aria attributes
  * refer to the WAI-ARIA

8. Use Accessibility tools
  * [axe](https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd) chrome extension
  * node module [axe-core](https://www.deque.com/axe/)

9. Use Polyfills / libraries
  * [inert.js](https://github.com/WICG/inert)
  * put some focus ring

### Introduction to Web accessibility by WCG

res: [https://www.w3.org/WAI/fundamentals/accessibility-intro/#context]()

#### What is web accessibility?

* Websites, tools, and technologies are designed and developed so that people with disabilities can use them:
  * auditory
  * cognitive
  * neurological
  * physical
  * speech
  * visual

* Can also benefit others without accessibility:
  * smart TVs with different types of inputs
  * ageing people that develop limitations
  * people with broken arm (_temporary disabilities_)
  * tough environments (_loud, too bright_)
  * slow internet environments

* Can aid for SEO