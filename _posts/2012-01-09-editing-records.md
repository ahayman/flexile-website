---
layout: page
title: Editing Records
category: [support]
---

Flexile uses a stateless system for managing changes to records. What this means is there is not such thing as an unsaved record. Changes you make to a record are saved as soon as you make them.

Backstory (if you're interested): It used to be that records could be in a "changed but not saved" state. This is actually pretty common for database systems and when I first created Flexile it seemed like a reasonable approach. But after using Flexile (gasp! yep, I eat the dog-food around here...) I began to realize that forcing the user to save changes they made is a little... hmmm, let's call it patronizing. I mean, why wouldn't you want to save the changes you've put all that hard work into? Plus, it's extra work hitting that "Save" button... you know? I want to make Flexile as easy as possible. So I moved to this stateless system where you never need to save a record. Of course, people make mistakes (don't tell mom) and Flexile will keep track of the changes you make to a record so you can undo them if you need to. I'll say this much, it makes making data entry a bit quicker now.

## Add a Record
To add a record, tap on the Add Record button (shown left). To edit a record tap on it in the record list. That's it, as well it should be. Editing a record is pretty much the same as adding a record, except you're changing existing data rather than adding new data. Just note that if when you do add a record it is immediately added to the database. So if you accidentally tap on the Add button, you'll have to delete the record.

## Making Changes
The Add Record screen is the same screen you'd use to edit a record, with the subtle (but not insignificant) distinction of an empty screen with no data for a new record.

Editing data is fairly easy to do. Tap on the Field whose data you want to change and that field will fill the screen and usually provide you some sort of input control (like a Keyboard or Calendar). Some controls won't have an input control (an Image, for example), but you'll still get buttons in the toolbar to add or change the image. You'll also be presented with a toolbar that separates the input control from the field. At the very minimum you'll see "Done", which will take you out of editing. If there is more than one field, you'll also see two additional controls: "<<" and ">>" (previous and next, respectively). You can use these to progress to the next/prev field (determined by the fields position on the screen). You can also swipe left/right on the field to achieve the same effect. There may be other buttons present on the toolbar, but they will be specific to the field type. For example, Note fields will have a button allowing you to dismiss the toolbar so you can view the note in full screen.

Once you leave the field you're editing, either by tapping Done or by progressing to the next field, the data will be saved. You can always undo later, but you don't need to worry about loosing your data.

### Undo
After you've altered a record, you should notice an undo button at the top right of the record's detail view (it'll look kind of like a clock moving backwards). You can use this to undo the changes you've made. Flexile keeps track of each discrete change you make to the record (a discrete change occurs when you exit the field by tapping Done or moving to another field).

### Redo
If you undo a change you've made to a record, Flexile will then create a Redo list. The redo button looks like a clock moving forward and it'll be place right next to the undo button. You can redo changes so long as you don't manually change the record. If you do manually make a change, the redo list will be discarded.

### Warning!
Flexile will keep track of undo changes as long as it remains it memory (the app isn't shut down). Once Flexile is shut down, all of the undo changes are lost. Note: Just because you leave the app doesn't mean it's shut down. iOS (the operating system) will shut it down if it needs memory or you can shut it down by double-tapping on the Home Button of your device and closing it.

## Pages
If a table has a lot of fields they may not all fit on the screen. If so, Flexile will automatically create new 'pages' to put the fields on (Note: you can also setup pages in custom views). The easiest way to access other pages is to simple swipe left (or right to go back) on the record. There will be a small indicator at the bottom of the record letting you know what page you're on. You can also select the tap you want by pulling down on the "Options Handle" (see below) until you see a list of tabs. Simple tap on the one you want to go to that page. Note: the Tab List won't be available if there is only one page.

## Links
You may notice, especially if you're using an iPad, there are Links you can add to the record. Of course, Links are one of the main features of Flexile. However, for now we're going to ignore it. We'll be going over links in another tutorial. But for now, you can add Link by tapping on the add button in the Links view, selecting the table and the record you want to link to. That's it. Of course, you'll want to visit the Links Tutorial for more information but this should get you started.

## Record Options
Toward the top of the record you should see a "grab handle". If you pull down on that grab handle you be presented with some buttons. All of these buttons will be explained below:

### New
This button will close the current record out and open a new, unsaved record. This will save you from closing out of the current record and opening up a new one. This button will only show up if the current record needs to be saved.

### Sharing
The sharing button will allow you to export this record in a variety of ways, which will be presented when you tap on the button. You can:

- Copy the text of the record to the device clipboard. This will allow you to paste the data in another app.
- Email the Record with no attachments. This means images and audio data will get left out.
- Email the Record with Attachments. Images and audio data will be appended as attachments.
- Email the Record with Links. This will email the record and include all Linked records. Note that this could make for a long email. This will not include any attachments.
- Email the Record with Links and Attachments. This will email the record with all Linked record as well as Attachments for the Record. This does not include attachments for the Links.
Note: Emails are sent as formatted HTML.

### Delete
Tapping on the Delete button will delete this record. You will get a warning to confirm the deletion.

## Record Navigation
### Record List
While you're viewing a Record's detail, Flexile can navigate between sequential records without having to revisit the record list. You will see one (or both) record navigation buttons if you can navigate between records. If you don't see a navigation button, this means either you're at the end of the list (only one button is present) or the current record is no longer in the list, which can happen if you edit/save the record and the list is filtered. This navigation will occur only within the current recordset (the records displayed in the list). You can also navigate between the records by dragging left or right on the navigation bar.

### Link History
When you're viewing a record, Flexile will also display alongside that record a list of all the other records it's linked to. You can "follow" a link by tapping on it and Flexile will display the Link's record along with it's links. Of course, you can continue to follow links to your hearts content and Flexile will keep track of all the past records you've been to. You can then navigate the link history using the buttons. Just as with record navigation, you can also navigate the link history by dragging the navigation bar left or right.

FYI - You can only navigate through a link history or the record list. Once you've started following links, you the navigation buttons will change to reflect Link Navigation.

## Closing the Record
Once you're done with the record you'll want a way out. There are a couple ways to do this:

- iPad: There will also be an "X" button at the very top-left of the modal screen for the iPad. This will close the current record.
- iPhone: On the iPhone there will be a back button at the top-left of the screen that will take you back to the record list.
- The Fun Way: I've gotta mention it: You can pinch the record close (pinch in or out, both ways work). You should try it at least once.... all the 'cool' kids are doing it!