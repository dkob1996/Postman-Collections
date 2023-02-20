## Booking - UpdateBooking<br>
Updates a current booking
### Put
We use curl form documentation, but we change info form documentation in '*' and '**' places.
```
* Here we change '1' to {{bookingID}}
** And here we change current token to variable {{token}}
```
```json
curl -X PUT \
  https://restful-booker.herokuapp.com/booking/{{bookingID}}          //*
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Cookie: token={{token}}' \                                      //**
  -d '{
    "firstname" : "James",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}'
```
Answer form server:
* Code 200 OK
* Info about our booking with updating info about us

### Add test<br>
All tests will add to tab 'Tests'.

* Test to check status 200 OK:
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

* Test to check new first name
```js
pm.test("Check new first name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.firstname).to.eql("James");
});
```

* Test to check new last name
```js
pm.test("Check new last name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.lastname).to.eql("Brown");
});
```