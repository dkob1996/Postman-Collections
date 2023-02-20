## Booking - DeleteBooking<br>
Returns the ids of all the bookings that exist within the API. Can take optional query strings to search and return a subset of booking ids.
### Delete
We use curl form documentation, but we change info form documentation in '*' and '**' places.
```
* Here we change '1' to {{bookingID}}
** And here we change current token to variable {{token}}
```
```json
curl -X DELETE \
  https://restful-booker.herokuapp.com/booking/{{bookingID}} //*
  -H 'Content-Type: application/json' \                      //**
  -H 'Cookie: token={{token}}'
```
Answer form server:
* Code 201 OK
* Message 'done'

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 201 OK:
```js
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});
```