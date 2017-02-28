#ionic
> Fix a bug for my project.

## code refactor (/release/js/ionic-angular.js):
+ delete:
```javascript
// TODO:1.delete by fei:
// if multitouch or regular scroll event, get out immediately
// if (!canOverscroll || e.touches.length > 1) {
//   return;
// }
```

+ modify:
```javascript
// TODO:2.modify by fei:`scrollParent.scrollTop !== 0`  ===> `scrollParent.scrollTop > 0`

// Do like this:
if (deltaY - dragOffset <= 0 || scrollParent.scrollTop > 0) {
  // ionic codes...
}
```
