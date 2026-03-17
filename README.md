<h2>Disclaimer:</h2>
<p>This is a fork of rnosov/react-reveal with fixes for React <code>^18.x.x</code> and <code>^19.x.x</code></p>
# React Reveal

[React Reveal](https://www.react-reveal.com/) is
an animation framework for React. It's MIT licensed, has a tiny footprint
and written specifically for React in ES6. It can be used to create various cool reveal
on scroll animations in your application.
If you liked this package, don't forget to star
the [Github repository](https://github.com/successtar/react-reveal).

## Live Examples

A number of simple effect examples:
- [Fade](https://www.react-reveal.com/examples/common/fade/)
- [Flip](https://www.react-reveal.com/examples/common/flip/)
- [Rotate](https://www.react-reveal.com/examples/common/rotate/)
- [Zoom](https://www.react-reveal.com/examples/common/zoom/)
- [Bounce](https://www.react-reveal.com/examples/common/bounce/)
- [Roll](https://www.react-reveal.com/examples/common/roll/)

Also, there are more complicated examples of [animated form errors](https://www.react-reveal.com/examples/advanced/form/) and a [todo app](https://www.react-reveal.com/examples/advanced/todo/).


## Full Documentation

For a full documentation please visit [online docs](https://www.react-reveal.com/docs/).

## Installation

In the command prompt run:

```sh
npm install @successtar/react-reveal --save
```

Alternatively you may use `yarn`:

```sh
yarn add @successtar/react-reveal
```

## Quick Start

Import effects from [React Reveal](https://www.npmjs.com/package/@successtar/react-reveal) to your project. Lets try `Zoom` effect first:

```javascript
import Zoom from '@successtar/react-reveal/Zoom';
```

Place the following code somewhere in your `render` method: 

```jsx
<Zoom>
  <p>Markup that will be revealed on scroll</p>
</Zoom>
```

You should see zooming animation that reveals text inside the tag. You can change this text to any JSX you want. If you place this code further down the page you'll see that it'd appear as you scroll down.

## Revealing React Components

You may just wrap your custom React component with the effect of your choosing like so:

```jsx
<Zoom>  
  <CustomComponent />
</Zoom>
```

In such case, in the resulting `<CustomComponent />` HTML markup will be wrapped in a `div` tag. If you would rather have a different HTML tag then wrap `<CustomComponent />` in a tag of your choosing:

```jsx
<Zoom>
  <section>
    <CustomComponent />   
  </section>
</Zoom>
```

or if you want to customize `div` props:

```jsx
<Zoom>
  <div className="some-class">
    <CustomComponent />   
  </div>
</Zoom>
```

## Revealing Images

If you want to reveal an image you can wrap `img` tag with with the desired `@successtar/react-reveal` effect:

```jsx
<Zoom>
  <img height="300" width="400" src="https://source.unsplash.com/random/300x400" />
</Zoom>
```

It would be a very good idea to specify width and height of any image you wish to reveal.

## Children

`@successtar/react-reveal` will attach a reveal effect to each child it gets. In other words,

```jsx
<Zoom>
  <div>First Child</div>
  <div>Second Child</div>
</Zoom>
```

will be equivalent to:

```jsx
<Zoom>
  <div>First Child</div>
</Zoom>
<Zoom>
  <div>Second Child</div>
</Zoom>  
```

If you don't want this to happen, you should wrap multiple children in a `div` tag:

```jsx
<Zoom>
  <div>
    <div>First Child</div>
    <div>Second Child</div>
  </div>
</Zoom>
```


## Server Side Rendering

`@successtar/react-reveal` supports server side rendering out of the box. In some cases, when the javascript bundle arrives much later than the HTML&CSS it might cause a flickering. To prevent this `@successtar/react-reveal` will not apply reveal effects on the initial load. 
Another option is to apply gentle fadeout effect on the initial render. You can force it on all `@successtar/react-reveal` elements by placing the following code somewhere near the entry point of your app:

```jsx
import config from '@successtar/react-reveal/globals';

config({ ssrFadeout: true });
```

Or you you can do it on a per element basis using `ssrFadeout` prop:

```jsx
<Zoom ssrFadeout><h1>Content</h1></Zoom>
```

One last option is to use `ssrReveal` prop. If enabled, this option will suppress both flickering and `ssrFadeout` effect. The unfortunate drawback of this option is that the revealed content will appear hidden to Googlebot and to anyone with javascript switched off. So it will makes sense for images and/or headings which are duplicated elsewhere on the page.

## Forking This Package

Clone the this repository using the following command:

```sh
git clone https://github.com/successtar/react-reveal.git
```

In the cloned directory, you can run following commands:

```sh
yarn install
```

yInstalls required node modules

```sh
yarn build
```

Builds the package for production to the `dist` folder

```sh
yarn test
```

Runs tests

## License

Copyright © 2022 Hammed Olalekan Osanyinpeju.

Credit: Roman Nosov 2018.

Project source code is licensed under the MIT license.
