Most of the time, database ids are generated using number. What happens if you have a feature for username that detects either the name or id exists? This will throw error when the username can be number, since we can't distinguish between id and name:

```js
function slugOrId() {}
```
