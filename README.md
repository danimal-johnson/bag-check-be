# Bagcheck backend

API for Bagcheck app.

Check-in procedure:
* Each guest is assigned a guest number/tag Number for the evening.
* All bags are stored under this number.
* Bikes, carts, and other large objects are stored in the locker outside.

## Tables



### Guest
* id: int, auto
* tagNum: int
* checkinAt: DateTime
* checkoutAt: DateTime
* FirstName: String
* LastName: String
* FirstTime: Boolean // Has the guest stayed another night this season?
* Paperwork: Boolean // If new, Has the guest filled out paperwork?

### Bag (Property?)
* id: int, auto
* tagNum: int
* description: text
* 

### BagAccess

* id: int, auto
* tagNum: int
* AccessedAt: DateTime
* Description: String (ex: "add bag", "accessed blue backpack", "retrieved bike")

## API

### /guests

* POST create guest
* PUT :id modify guest
* GET :id { (Guest info) }

### /reports

* GET guest_stats
  { unique, first_time, beds_filled, }
* GET guest_list
  [{user, }]
* GET bag_access
  { guest_name, bag_number, check-in, [bag accesses], check-out }
*

## Future expansion

1. Roles: check-in desk, bag-check, bike cage, medical, ...
2. Medical and incident reports
3. Authentication and authorization
4.