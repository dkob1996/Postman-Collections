## Discription:
We copy [Auth]() form the positive cases.
And after that we delete info in tab 'body':
```
We delete (*) info in body, and now it's invalid.
```
```json
{
    //*
}
```
## Results:
* At first - answer:
```json
{
    "reason": "Bad credentials"
}
```
* Code server 200 OK

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 200 OK:
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

* Find message 'Bad Credential' in answer from server.
```js
pm.test("Match with sentence 'Bad credentials' in body", function () {
    pm.expect(pm.response.text()).to.include("Bad credentials");
});
```

* Find message 'Bad Credential' in container 'reason' (it works if we know name of container. if we don't know we need to use previous test).
```js
pm.test("Match with sentence 'Bad credentials' in container 'reason'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.reason).to.eql("Bad credentials");
});
```