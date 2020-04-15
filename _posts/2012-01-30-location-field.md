---
layout: page
title: Location Field
category: [field]
---

The location field will store addresses as well as GPS location (Latitude/Longitude) and display a map you can use to set the position of an address, search for an address and edit an address.  Note that the map will only work if you have an internet connection or (on occasion) if the address location happens to be cached in Apple's maps (hey, it happens...).

## Data Entry
To edit (or add) an address, tap on the address field to open it full screen. If an address has already been entered, Flexile will attempt to open the map to the address. However, this can fail if there is no internet connection. Still, even without an internet connection you'll be able to edit the address.

After opening the map field, you'll see a search bar at the top.  You can use the search field to add a new address or replace the current address.  After you search, Flexile will attempt to find the address and, having found it, it will fill in any missing data with a complete address.  If it can't find the address (or there is no internet connection) you'll get a warning, but the address you entered will still be used in the field.

### Locate Yourself
You can also have Flexile locate your current position.  Use the "cross hairs" button on the toolbar (shown right).  Note that you'll be asked to give Flexile permission to use your Location the first time you attempt to use the location service.  

### Driving Directions & Map Apps
You can open the current address in another app, depending on what you have installed. Tapping on the share button will give you a few options:

- Apple Maps:  This will open the current address in Apple's Maps app.
- Apple Directions:  This will open Apple Maps to the current location  and set the driving directions to the address. 

The following will also be available if you have the Google Maps app installed.  Otherwise, you'll only get the Apple maps options: 

- Google Maps:  This will open the current address in Google Maps app. 
- Google Directions: This will open the Google Maps app to the current location  and set the driving directions to the address.

Note:  The GPS location coordinates of the address is passed to Google Maps, so you won't see the actual address listed, although often Google will translate the address into a Name if it has one.

After Flexile finds the address, it will alter the map to the address it found and add an annotation to the map indicating it's position, address and the Latitude/Longitude position.  The address presented will probably be altered from the original search term you provided (hopefully, it'll be more accurate).  

Note: Currently, the search results are provided by Google.  Give a search term, Flexile will use the first (most likely) result provided by Google. 

## Editing an Address

The address in the annotated view will be used for the field.  If you wish, you can alter the provided address by tapping on it. Whatever you alter the address to is what the field will store.  However, the field will retain the Latitude/Longitude, so the position of the address will remain unchanged, no matter how you alter the address.

Finally, you can alter the actual position by dragging the map point around.  When you do, the Latitude and Longitude will update to the new location. You can use this to move the map icon to more accurate results if the search proves... inadequate.  