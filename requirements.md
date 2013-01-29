# Requirements

## Import Inventory

- CSV file for importing inventory
  - arbitrary format or fixed format?
- via email
- via Dropbox?

## Inputting other data

- enter new client (import or just enter)
  - select from contacts?
- enter new band
  - select from contacts?


## View Inventory

  
- view by category
- view by brands (within a category)
- view available between start and stop date


## Create Rental List for a Gig

- make a new gig
  - select client
  - select band
  - enter date
  - select items for the gig


## View a gig

- show client
- show band
- show list of equipment

## Get items for a gig?

- scan/mark off items as they are found and loaded?


## Delivery

- mark items that were delivered
- be able to scan items that are dropped off to confirm?

## Pickup

- mark items that were picked up
- be able to scan items as they are picked up?


## Merge/Sync Delivery and Pickup 


## Reports

- given a client, produce list of past and future gigs
- given a band, produce list of past and future gigs
- given an inventory item, produce gigs it was used at

## Mileage tracking

- associate with a gig?
- record mileage for a trip?


# Model Design

## Inventory object

  > fields
  
  >> category (amps, instruments)

  >> name
  
  >> condition
  
  >> description
  
  >> note
  
  >> ID for barcode/QR code
  
  >> quantity
  
  >> accessor field?
  
  >> flag for borrowed inventory 
  
 > relations

   >> to many gigInventory
   
## Client object

  > fields
  
  >> name
  
  >> contact
  
  >> note
  
  >> photo
  
 > relations
 
  >> to many gig
  
## Band object

  > fields
  
  >> name
  
  >> note
  
  >> contact name

  >> contact phone
  
  >> photo(s)?
  
  > relations
  
  >> to many gig
  
## Gig object
  > fields
  
  >> address
  
  >> drop off date/time
  
  >> pick up date/time
  
  >> note
  
  > relations
  >> to one client
  
  >>to one band (can be nil?)
  
  >> to one gig
  
  >> to many gigInventory
  
## GigInventory
  > fields
  
  >>	
  
  > relations
  
  >> to 1 gig
  
  >> to 1 inventory

