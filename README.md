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
* Description: String (ex: "add bag", "accessed blue backpack", "retrieved bike"


## API

### Guest
* POST new guest
* PUT modify guest
* GET lookup guest


