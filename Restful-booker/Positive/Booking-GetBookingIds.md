## Booking - GetBookingIds<br>
Returns the ids of all the bookings that exist within the API. Can take optional query strings to search and return a subset of booking ids.
### Get
We use curl form documentation:
```json
curl -i https://restful-booker.herokuapp.com/booking
```
Answer form server:
* Code 200 OK
* So much booking id's

### Add test<br>
We can add status test in tab 'tests':
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
