```js
// Underscore's each function (roughly)
var each = function(obj, iterator, context) {
  if (obj == null) return;
  if (Array.prototype.forEach && obj.forEach === Array.prototype.forEach) {
    obj.forEach(iterator, context);
  } else if (obj.length === +obj.length) {
    for (var i = 0, l = obj.length; i < l; i++)
      iterator.call(context, obj[i], i, obj);
  }
};

each([1, 2, 3, 4], function(n) {
  n; //: number
  this; //: Date
}, new Date);

each([{x: 10}], function(o) {
  o; //: {x}
  this; //: String
}, new String("x"));
```
```json
[
  {
    "name": "each",
    "addr": "/each/",
    "kind": "f",
    "type": "void function(Array[each.!0.<i>], fn(o: each.!0.<i>)",
    "lineno": 2
  }
]
```
```ctags
each		/each/;"	f	lineno:2	type:void function(Array[each.!0.<i>], fn(o: each.!0.<i>)
```
