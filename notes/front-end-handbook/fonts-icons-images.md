## Images

### Responsive images by MDN

res: [https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive images]()

#### Problems

- Art Direction problem - images become cropped on smaller devices
- Resolution switching problem - its a waste to load a high res image for desktop on mobile because it wastes resources

#### Solutions

- Resolution Switching solution - Use `srcset` attr to switch resolutions for images with different viewports
  e.g.

  ```html
  <img srcset="elva-fairy-320w.jpg 320w,
              elva-fairy-480w.jpg 480w,
              elva-fairy-800w.jpg 800w"
      sizes="(max-width: 320px) 280px,
              (max-width: 480px) 440px,
              800px"
      src="elva-fairy-800w.jpg" alt="Elva dressed as a fairy">
  ```

  - [Same size different resolution technique](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images#Resolution_switching_Same_size_different_resolutions)

- Art Direction Solution - Use `<picture>` tag to load a cropped photo of your choice
  e.g.
  ```html
  <picture>
    <source media="(max-width: 799px)" srcset="elva-480w-close-portrait.jpg">
    <source media="(min-width: 800px)" srcset="elva-800w.jpg">
    <img src="elva-800w.jpg" alt="Chris standing up holding his daughter Elva">
  </picture>
  ```

#### Tools

- Use responsive design mode to know the pixels
- Use the network tools to know how large the photo is

#### More tips

- Why not use CSS or JS??

  - On the average, it shaves off 20% of loading time - because browser engine preloads images in HTML before parsing css and js
  - Image is loaded by then when you use js

- `<picture>` lets you cater to modern image formats and have a fallback too
