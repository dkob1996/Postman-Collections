## Discription:
We copy [Booking Update]() form the positive cases.
And after that we rewrite info in field cookie with parameter 'token' in tab 'header' and change {{token}} to 1234555:

## Results:
* At first - answer:
```json
Forbidden
```
* Code server 403 Forbidden

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 403 Forbidden:
```js
pm.test("Status code is 403", function () {
    pm.response.to.have.status(403);
});
```