## Discription:
We copy [Booking Update]() form the positive cases.
And after that we change {{bookingID}} to '0':
```
We change it here (*).
```
```json
https://restful-booker.herokuapp.com/booking/0    //*
```
## Results:
* At first - answer:
```json
Method Not Allowed
```
* Code server 405 Method Not Allowed

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 405 Method Not Allowed:
```js
pm.test("Status code is 405", function () {
    pm.response.to.have.status(405);
});
```