---
layout: page
title: Reference Field
category: [field]
---

The reference field is a simple but powerful field that allow you to reference another table field.  It pulls its data through through either the first or last link for each record and displays the data in the same control the referenced field uses.

You can chain reference fields together by referencing another reference field.  When a referenced field changes, the updates are cascaded to all referencing fields, including through "chains" of reference fields. A reference field cannot edit the data it references, though it does provide a control to easily change the record it references to.  This effectively turns the reference field into a kind of Pick List that uses other tables as the "pick" items.

## Options

- Reference Field:  Tap this button to select the table and field you want to reference.  You can  reference other reference fields so long as doing so doesn't create a cyclical reference.  If Flexile detects that referencing a field would cause a cyclical reference, it won't list that field for selection.
- Pull Data From:  This allows you to choose whether Flexile will pull data from the First Link or Last Link.  
- Auto Save Selection:  Reference fields provide a button to easily select the record you want to reference. This option is a convenience option for how you select the record. If this option is not checked, you have to tap on the "Save" button after making a selection. If this option is selected, when you tap on a record it will be selected and saved immediately.
- Table Aggregate (not shown): You will only get this option if you reference a number based field.  If so, you can choose to display aggregate information for this field at the bottom of the table.  
 
## Selection
The reference field will automatically pull data from the first (or last) link made to the table of the field you're referencing.  So you can change a referenced field's data by changing the record's links and it'll update. Reference fields also provide an option to directly change which record they're referencing.

When you're editing a record, you'll see either a "Linked" or "UnLinked" icon in the reference field. Tapping on the icon will open up a record selector you can use to change (if the field's already linked) or add a Linked reference.  When you do select a reference, Flexile will either:

- If there are no Links, the selected record will be added as a link.
- If there is one Link Flexile will check if there are other fields referencing the link using a different "pull".  If another field is referencing the Linked record under a different "pull" then Flexile will insert a new Link so as not to disturb the existing Link.  If there are no other referencing Fields, Flexile will replace the current Link with the new one.
- If there are existing Links (plural) Flexile will replace the referencing Link with the selected one. 
