tmix-caching
============

AngularJS service that extends the $cacheFactory with time out functionality.



## Usage

__Step 2: Add the Dependencies in Index.html__


```
<script src="bower_components/tmix-caching/tmixCaching.js"></script>
```

__Step 3: Add tmixCaching as a Dependency in App.js__

```
angular.module('MYAPPNAME', [
  'ngCookies',
  'ngResource',
  'ngSanitize',
  'ngRoute',
  'ngAnimate',
  'angulartics.google.analytics',
  'tmixCaching'
])
...
```


__Step 4: Add the Dependency Where Necessary__


```
// Example adding tmixCaching dependency
angular.module('myApp')
  .factory('myService', function(tmixCaching) {
    // Service logic
    // ...
  });
```


## Methods

Extends angular's $cacheFactory with time based functionality.  Allows for setting a timeout on cache objects. There are six methods available in this service.

### destroy()

__destroy(name)__

Removes an object from angular's cache.

* name (required): string

__Sample Code Snippet Using destroy()__

```
intcCaching.destroy('myCache');
```

### get()

__get(name)__

Returns the specified object from cache.  Will return a null if the object does not exist or has timed out.

* name (required): string
* _Returns the specified object from cache_

__Sample Code Snippet Using get()__

```
var myData = intcCaching.get('myCache');
```

### getAsCopy()

__getAsCopy(name)__

Returns a copy of the specified object from cache.  Will return a null if the object does not exist or has timed out.

* name (required): string
* _Returns a copy of the specified object from cache_

__Sample Code Snippet Using getAsCopy()__

```
var myData = intcCaching.getAsCopy('myCache');
```

### getTimeout()

__getTimeout(name)__

Returns the specified object's millisecond timeout value.  Will return a null if the object does not exist.

* name (required): string
* _Returns the specified object's millisecond timeout value_

__Sample Code Snippet Using getTimeout()__

```
var myDataTimeout = intcCaching.getTimeout('myCache');
```

### getTimeStamp()

__getTimeStamp(name)__

Returns the specified object's timestamp from when it was put in cache.  Will return a null if the object does not exist.

* name (required): string
* _Returns the specified object's timestamp from when it was put in cache_

__Sample Code Snippet Using getTimeStamp()__

```
var myDataTimeStamp = intcCaching.getTimeStamp('myCache');
```

### isValid()

__isValid(name)__

Returns a boolean indicating if the object is in cache and is still valid (within the timeout value).

* name (required): string
* _Returns a boolean indicating if the object is valid_

__Sample Code Snippet Using isValid()__

```
var myDataValid = intcCaching.isValid('myCache');
```

### put()

__put(name, value, milliseconds)__

Puts an object into angular's cache with an optional timeout value.  If a millisecond timeout is included, the get method will test against the millisecond timeout value. If millisecond timeout value is not included, the get method will always return the value object.

* name (required): string
* value (required): primitive/object
* milliseconds (optional): integer

__Sample Code Snippet Using put() with a one hour timeout value__

```
intcCaching.put('myCache', myObjectToPutInCache, 3600000);
```

__Sample Code Snippet Using put() with no timeout value__

```
intcCaching.put('myCache', myObjectToPutInCache);
```  
  
### putAsCopy()

__putAsCopy(name, value, milliseconds)__

Puts a copy of an object into angular's cache with an optional timeout value.  If a millisecond timeout is included, the get method will test against the millisecond timeout value. If millisecond timeout value is not included, the get method will always return the copy of the value object.

* name (required): string
* value (required): primitive/object
* milliseconds (optional): integer

__Sample Code Snippet Using putAsCopy() with a one hour timeout value__

```
intcCaching.putAsCopy('myCache', myObjectToPutInCache, 3600000);
```

__Sample Code Snippet Using putAsCopy() with no timeout value__

```
intcCaching.putAsCopy('myCache', myObjectToPutInCache);
```

## SecurityProvider.js

Add custom authorization to Angular to secure access to controllers and control visibility of UI elements within the views. For usage details, see https://github.intel.com/5Star/intcNg/wiki/Security-Provider.

---

Please submit questions, suggestions, and bugs to the [repo's Issues log](https://github.intel.com/5Star/intcNg/issues).


