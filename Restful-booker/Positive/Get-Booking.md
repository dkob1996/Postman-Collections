## Booking - GetBooking<br>
Returns a specific booking based upon the booking id provided
### Get
We use curl form documentation, but we change info form documentation in '*' place.
```
* Here we change '1' to {{bookingID}}
```
```json
curl -i https://restful-booker.herokuapp.com/booking/{{bookingID}} //*
```
Answer form server:
* Code 200 OK
* Info about our booking

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 200 OK:
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```