---
title:  deepFlatten
tags: array,recursion,intermediate
---

Deep flattens an array.

Use recursion.
Use `array_merge` with an empty array to flatten the array.
Recursively flatten each element that is an array.

```php
function deepFlatten($items)
{
  $result = [];
  foreach ($items as $item) {
    if (!is_array($item)) {
      $result[] = $item;
    } else {
      $result = array_merge($result, deepFlatten($item));
    }
  }

  return $result;
}
```

```php
deepFlatten([1, [2], [[3], 4], 5]); // [1, 2, 3, 4, 5]
```
