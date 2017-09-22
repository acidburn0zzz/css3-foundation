# 55 Minutes CSS3/HTML5 Foundation

This project is a CSS3/HTML5 template for crafting modern web applications. This latest iteration of the template is well-suited for building simple static websites, or serving as the foundation for web applications. For a React/Redux-based application, see my [create-react-app-based starter project](https://github.com/ravasthi/yaras).

To use this project, you should have a recent (>= 8.0) version of [node.js](https://nodejs.org/) installed.

## Feature Highlights

* A fluid, responsive layout following the principles of [Responsive Web Design](http://www.abookapart.com/products/responsive-web-design "A Book Apart, Responsive Web Design").
* Best practices recommended by various boilerplate projects, as well as our own experience developing web applications.
* A style guide containing examples of the default styles defined in the project.
* A number of convenient Sass mixins for:
    * Clearfix
    * Inline lists
    * Lists with colored bullets
    * Retina images
    * Text size/line height combinations
    * [Pure CSS parallax scrolling](http://keithclark.co.uk/articles/pure-css-parallax-websites/ "Pure CSS Parallax Websites by Keith Clark")
* Integration with the [Susy layout framework](http://susy.oddbird.net).
* Integration with [Font Awesome](http://fontawesome.io "Font Awesome, the iconic font and CSS toolkit").
* Sass linting with [stylelint](https://stylelint.io).
* Dependency management with [npm](https://www.npmjs.com)/[yarn](https://yarnpkg.com/).
* Asset bundling with [webpack](https://webpack.js.org).
* Integration with [Browsersync](https://www.browsersync.io) for *really* painless development.

## Getting Started

1. Install node.js, or verify that it is already installed.
2. Change into the <code>css3-foundation/</code> directory in your favorite terminal application and type <code>npm install</code>.
3. Steps 1–2 are one-time-only setup requirements. Hereafter, all you need to do is run the following command from <code>css3-foundation/</code>:

        npm run start

    This will monitor changes to your source files, recompile the Sass and JavaScript, and (re)load your browser. To compile the scripts and styles one time only, type:

        npm run build

    See all available npm scripts:

        npm run

## File organization

Files in this project are organized into directories like so:

    css3-foundation/
    ├── distribution
    │   ├── fonts
    │   ├── scripts
    │   └── styles
    ├── images
    │   ├── app-icons
    │   └── originals
    └── source
        ├── scripts
        │   └── vendor
        └── styles
            ├── basics
            └── shared

Please refer to individual source files for details on what should be included there, but here are some general guidelines for file organization:

* **source/** contains the Sass and JavaScript source files that Webpack will combine/compile
    * **source/styles/** contains the Sass source files. We use the SCSS syntax for this project.
        * **source/styles/basics/** contains the building blocks of our styles: the colors, the typography, the grid.
        * **source/styles/shared/** contains application-wide styles like header, footer and form styles. Default styles for the basic HTML tags should also be included here.
    * **source/scripts/** contains all of the project's JavaScript files. Put custom JavaScript at the top level of this directory.
        * **source/scripts/vendor/** contains custom-built libraries like Modernizr. npm/yarn-installed libraries are, of course, in **node_modules/**.
* **distribution/** will contain the processed asset files that are included by the HTML files
    * **distribution/styles/** contains the compiled stylesheets, the CSS files that we will include in our markup. The contents of this directory are not checked into source control, but will be generated by Webpack when you run `npm run build`.
    * **distribution/scripts/** contains the compiled JavaScript files, the JS files that we will include in our markup. The contents of this directory are not checked into source control, but will be generated by Webpack when you run `npm run build`.

## CSS rule organization &amp; linting

A single CSS rule set can quickly grow large and unwieldy, so to promote ease of reading, we recommend following a prescribed order for writing your CSS rules. In general, we work from the outside in, from layout to text:

```css
selector
{
  /* Display and positioning */
  display: …;
  visibility: …;
  position: …;
  top: …;
  right: …;
  bottom: …;
  left: …;
  z-index: …;
  clear: …;
  float: …;

  /* Transforms and animations */
  transform: …;
  animation: …;
  transition: …;

  /* Box model/layout */
  box-*: …;
  margin: …;
  outline: …;
  border: …;
  padding: …;
  width: …;
  min-width: …;
  max-width: …;
  height: …;
  min-height: …;
  max-height: …;
  overflow: …;
  clip: …;
  resize: …;
  table-layout: …;

  /* Alignment */
  vertical-align: …;
  text-align: …;

  /* Background/foreground color */
  background: …;
  color: …;
  opacity: …;

  /* Text properties */
  font-family: …;
  font-size: …;
  line-height: …;
  direction: …;
  font-style: …;
  font-variant
  text-decoration: …;
  text-indent: …;
  text-transform: …;
  letter-spacing: …;
  word-spacing: …;
  word-break: …;
  word-wrap: …;
  quotes: …;
  page-breakpointsak-*: …;
  list-style: …;
  white-space: …;
}
```

This is of course not required; some teams prefer, for example, to alphabetize the rules instead. The important thing is that whatever your team chooses, there is a consistent, documented pattern. We define our preferred order in this repository's `stylelint.config.js` and enforce it through stylelint and the [stylelint-order plugin](https://www.npmjs.com/package/stylelint-order).

