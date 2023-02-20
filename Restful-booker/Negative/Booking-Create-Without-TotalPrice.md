## Discription:
We copy [Create Booking]() form the positive cases.
And after that we delete one string 'totalprice' in tab 'body':
```
We delete (*) string 'totalprice', and now it's invalid.
```
```json
{
    "firstname" : "Jim",
    "lastname" : "Boot",
                               //*
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
Internal Server Error
```
* Code server 500 Internal Server Error

### Add test<br>
Test will add to tab 'Tests'.

* Test to check status 500 Internal Server Error:
```js
pm.test("Status code is 500", function () {
    pm.response.to.have.status(500);
});
```