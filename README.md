# vue-scale-transition-example

Example Vue project demonstrating a bug with transitions and scale. Increasing the scale (i.e. by dragging the browser/ window edge) will eventually cause the z-index to break, leading to an absolutely positioned div to be covered by the divs in the transitions. This bug appears in Chrome, but doesn't seem to be apparent in Firefox. Video example can be found here: https://gofile.io/?c=4HwzAT

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```
