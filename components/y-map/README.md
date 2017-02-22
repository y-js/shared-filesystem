
# Map Type for [Yjs](https://github.com/y-js/yjs)

Manage map-like data with this shareable map type. You can insert and delete arbitrary objects (also custom types for Yjs).

## Use it!
Retrieve this with bower or npm.

##### Bower
```
bower install y-map --save
```

##### NPM
```
npm install y-map --save
```

# Y.Map
Y.Map mimics the behaviour of a javascript Object. You can create, update, and remove properies on this type. Furthermore, you can observe changes on this type as you can observe changes on Javascript Objects with [Object.observe](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/observe) - an ECMAScript 7 proposal ~~which is likely to become accepted by the committee~~. Until then, we have our own implementation.

##### Reference
* .get(key)
  * Retrieve the value for key. If the value is a type, `.get(key)` returns a promise. Otherwise it returns the value
* .getPrimitive(key)
  * Retrieve the value for a key, if it is a primitive value (not a shared type - e.g. a number, string, or javascript object)
* .getType(key)
  * Retrieve the value for a key, if it is a shared type (e.g. when created with `map.set(key, Y.Text)`)
  * Always returns a Promise (is rejected when no value that is a type exists)
* .set(key, value)
  * Set/update a property. `value` may be a primitive type, or a custom type definition (e.g. `map.set(key, Y.Map)`)
* .delete(key)
  * Delete a property
* .keys()
  * Returns all keys for all values
* .keysPrimitives()
  * Returns all keys for all primitive values
* .keysTypes()
  * Returns all keys for all type values
* .observe(observer)
  * The `observer` is called whenever something on this object changes. Throws *add*, *update*, and *delete* events
* .observePath(path, observer)
  * `path` is an array of property keys
  * `observer` is when the value under the path is found.
  * `observer` is called when the property under `path` is set, deleted, or updated
* .unobserve(f)
  * Delete an observer

# A note on intention preservation
When users create/update/delete the same property concurrently, only one change will prevail. Changes on different properties do not conflict with each other.

# A note on time complexities
* .get(key)
  * O(1)
* .set(key, value)
  * O(1)
* .delete(key)
  * O(1)
* Apply a delete operation from another user
  * O(1)
* Apply an update operation from another user (set/update a property)
  * Yjs does not transform against operations that do not conflict with each other.
  * An operation conflicts with another operation if it changes the same property.
  * Overall worst case complexety: O(|conflicts|!)

## License
Yjs is licensed under the [MIT License](./LICENSE.txt).

<kevin.jahns@rwth-aachen.de>