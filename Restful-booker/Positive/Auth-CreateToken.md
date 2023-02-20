## Auth - CreateToken<br>
Creates a new auth token to use for access to the PUT and DELETE /booking
### Post
We use curl from documentation to import:
```json
https://restful-booker.herokuapp.com/auth
```
We create one variable form tab 'Variables':<br>
* Token<br>

And we should add in Auth in tab 'Tests':
```js
var jsonData = pm.response.json();
pm.collectionVariables.set("token",jsonData.token);
```
Now when we'll do authorization we'll save token number in postman's memory.

### Add test
We can add test to check status of operation in tab 'Tests'.
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```