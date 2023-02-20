## Booking - PartialUpdateBooking<br>
Updates a current booking with a partial payload
### Patch
We use curl form documentation, but we change info form documentation in '*' and '**' places.
```
* Here we change '1' to {{bookingID}}
** And here we change current token to variable {{token}}
```
```json
curl -X PATCH \
  https://restful-booker.herokuapp.com/booking/{{bookingID}} /*
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Cookie: token={{token}}' \                             /**
  -d '{
    "firstname" : "James",
    "lastname" : "Brown"
}'
```

Answer form server:
* Code 200 OK
* Info about our booking