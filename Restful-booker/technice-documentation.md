## Auth - CreateToken<br>
Creates a new auth token to use for access to the PUT and DELETE /booking
### Post
```json
https://restful-booker.herokuapp.com/auth
```
```json
curl -X POST \
  https://restful-booker.herokuapp.com/auth \
  -H 'Content-Type: application/json' \
  -d '{
    "username" : "admin",
    "password" : "password123"
}'
```
Response:
```json
HTTP/1.1 200 OK

{
    "token": "abc123"
}
```
## Booking - GetBookingIds<br>
Returns the ids of all the bookings that exist within the API. Can take optional query strings to search and return a subset of booking ids.
### Get
```json
https://restful-booker.herokuapp.com/booking
```
```json
curl -i https://restful-booker.herokuapp.com/booking
```
Response:
```json
HTTP/1.1 200 OK

[
  {
    "bookingid": 1
  },
  {
    "bookingid": 2
  },
  {
    "bookingid": 3
  },
  {
    "bookingid": 4
  }
]
```
## Booking - GetBooking<br>
Returns a specific booking based upon the booking id provided
### Get
```json
https://restful-booker.herokuapp.com/booking/:id
```
```json
curl -i https://restful-booker.herokuapp.com/booking/1
```
Json Response:
```json
HTTP/1.1 200 OK

{
    "firstname": "Sally",
    "lastname": "Brown",
    "totalprice": 111,
    "depositpaid": true,
    "bookingdates": {
        "checkin": "2013-02-23",
        "checkout": "2014-10-23"
    },
    "additionalneeds": "Breakfast"
}
```
## Booking - CreateBooking<br>
Creates a new booking in the API
### Post
```json
https://restful-booker.herokuapp.com/booking
```
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
Json Response:
```json
HTTP/1.1 200 OK

{
    "bookingid": 1,
    "booking": {
        "firstname": "Jim",
        "lastname": "Brown",
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
## Booking - UpdateBooking<br>
Updates a current booking
### Put
```json
https://restful-booker.herokuapp.com/booking/:id
```
```json
curl -X PUT \
  https://restful-booker.herokuapp.com/booking/1 \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Cookie: token=abc123' \
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
Json Response:
```json
HTTP/1.1 200 OK

{
    "firstname" : "James",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
```
## Booking - PartialUpdateBooking<br>
Updates a current booking with a partial payload
### Patch
```json
https://restful-booker.herokuapp.com/booking/:id
```
```json
curl -X PATCH \
  https://restful-booker.herokuapp.com/booking/1 \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Cookie: token=abc123' \
  -d '{
    "firstname" : "James",
    "lastname" : "Brown"
}'
```
Json Response:
```json
HTTP/1.1 200 OK

{
    "firstname" : "James",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
```
## Booking - DeleteBooking<br>
Returns the ids of all the bookings that exist within the API. Can take optional query strings to search and return a subset of booking ids.
### Delete
```json
https://restful-booker.herokuapp.com/booking/1
```
```json
curl -X DELETE \
  https://restful-booker.herokuapp.com/booking/1 \
  -H 'Content-Type: application/json' \
  -H 'Cookie: token=abc123'
```
Json Response:
```json
HTTP/1.1 201 Created
```
## Ping - HealthCheck<br>
A simple health check endpoint to confirm whether the API is up and running.
### Get
```json
https://restful-booker.herokuapp.com/ping
```
```json
curl -i https://restful-booker.herokuapp.com/ping
```
Response:
```json
HTTP/1.1 201 Created
```