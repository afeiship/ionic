# ionic
> Fix a bug for my project based on 1.3.2 + ng1.5.3.

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

+ modify:
```javascript
  function onInfinite() {
    ionic.requestAnimationFrame(function() {
      $element[0].classList.add('active');
    });
    // self.isLoading = true;
    //modify by fei:
    self.isLoading = self.jsScrolling;
    $scope.$parent && $scope.$parent.$apply($attrs.onInfinite || '');
  }
```


+ ionic.js
```javascript
// container.style.height = scrollViewOffsetHeight + "px";
```

