---
layout: default
title: "Laravel redirect all mistyped URLS"
date: 2016-08-11
---

[Laravel Daily](http://laraveldaily.com/routes-file-redirect-everything-else-to-homepage/



```
Route::any('{query}', 
  function() { return redirect('/'); })
  ->where('query', '.*');
  ```
