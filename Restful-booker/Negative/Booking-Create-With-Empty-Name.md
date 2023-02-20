## Discription:
We copy [Create Booking]() form the positive cases.
And after that we delete info in tab 'body':
```
We delete (*) info in 'firstname' and 'lastname', and now it's invalid.
```
```json
{
    "firstname" : "",             //*
    "lastname" : "",              //*
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
```
## Results:
* At first - answer:
```json
{
    "bookingid": 4382,
    "booking": {
        "firstname": "",
        "lastname": "",
        "totalprice": 111,
        "depositpaid": true,
        "bookingdates": {
            "checkin": "2018-01-01",
            "checkout": "2019-01-01"
        },
        "additionalneeds": "Breakfast"
    }
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

* Test to check empty first name:
```js
pm.test("Empty first name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.booking.firstname).to.eql("");
});
```

* Test to check empty last name:
```js
pm.test("Empty last name", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.booking.lastname).to.eql("");
});
```