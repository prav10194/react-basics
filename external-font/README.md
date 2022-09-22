## Install webfont package

## Add the font in your JS

```js
import WebFont from 'webfontloader';
```

```js
useEffect(() => {
    WebFont.load({
      google: {
        families: ['IBM Plex Serif']
      }
    });
   }, []);
```

## Use the font in CSS and HTML

```css
.font-loader {
    font-family: 'IBM Plex Serif', serif;
  }
```

```js

const Component = () => {
  
  return (
  <div className="font-loader">Hello World!</div>
  )
}

```
