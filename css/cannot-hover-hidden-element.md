# You Cannot Hover on a hidden element

```css
.container {
  opacity: 0;
}
.container:hover {
  opacity: 1;
}
```

The above works but
```css
.container {
 visibility: hidden;
}
.container:hover {
   visibility: visible;
}
```

Will not work because the over event will not trigger.

### Why?
With the `visibility: hidden` rule, the element in question will still occupy physical space on the page. It may seem all this rule does is hide the element, similar to `opacity:0` but in reality it behaves more like `display:none`.
Any interactive elements loos their ability to be interactied with. so although our `.container` has physical space, it can’t be interacted with in any way, hence no hover event occurs

#### Whats the point then?
The main reason for the `visibility: hidden` rule is not just about visual visibility is because it affects the elements visibility to assistive technology. It makes things invisibilie to technologies like screen readers.
