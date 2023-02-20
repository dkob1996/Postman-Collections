## Booking - CreateBooking<br>
Creates a new booking in the API
### Post
We use curl form documentation:
```json
curl -X POST \
  https://restful-booker.herokuapp.com/booking \
  -H 'Content-Type: application/json' \
  -d '{
    "firstname" : "Jim",
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
* Info about our booking

We need to create one variable in tab 'variables':
* bookingID

And we need add in tab 'Tests' code to save our bookingID in memory of Postman API.
```js
var jsonData = pm.response.json();
pm.collectionVariables.set("bookingID",jsonData.bookingid);
```

### Add test<br>
All tests will add to tab 'Tests'.

* Test to check status 200 OK:
```js
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```

* Test to check first name
```js
pm.test("Check first name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.booking.firstname).to.eql("Jim");
});
```

* Test to check last name
```js
pm.test("Check last name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.booking.lastname).to.eql("Boot");
});
```

* Test to check price
```js
pm.test("Check price", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.booking.totalprice).to.eql(111);
});
```