## Discription:
We copy [Booking Update](https://github.com/dkob1996/Postman-Collections/blob/main/Restful-booker/Positive/Booking-Update.md) form the positive cases.
And after that we exclude field cookie with parameter 'token' in tab 'header':

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