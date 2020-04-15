---
layout: page
title: Text Field
category: [field]
---

There are several field types that are variations of the "text field" including: 

- A Standard Text Field

- Note Field

Note that the following are also Text Fields, but we discuss them in a separate page.  However, everything discussed below also applies to these fields: 

- Email Address

- Website/URL

I'll be going over each of these fields in a little more detail below.  But before I do, I want to spend a little time talking about how to interact with text in Flexile.   

## Interacting with Text
In order to interact (edit) text, you've gotta first tap on the field you want to edit.  This should expand the field to fill the screen.  If the field isn't filling the screen, then you aren't editing it. Once you've opened a field for editing, there's a few gestures that make interacting with text easier.

### Scrolling
If there is more text than the field can display on screen then the text field will be scrollable.  Note Fields will scroll vertically (the text wraps).  All other fields will scroll horizontally.

### Moving the Cursor
You can move the cursor around by tapping on the screen.  Flexile will place the curse as close as it can to your finger.  I know, everyone knows this, but I figured I'd put it in here for completion. 

You can also move the cursor by dragging your finger around on the screen.  Just be aware that this may not always work if the text is larger than the field.  If it is, the view may scroll around instead of moving the cursor.  In that case, "Tap & Hold" on the text first and then drag around.

### Text Magnifier
If you "Tap & Hold" on any part of the text, a "Magnified" overlay of that text will appear above your finger. This is not the "standard" magnifying loupe Apple provides, but instead "snaps" itself to the line the cursor is on.  The magnifier also extends the entire width of the field, which makes it a lot easier to navigate around (it gives you context to where your finger actually is in the text).  Finally, you can drag your finger around for precise cursor placement.

The text magnifier will also be displayed if you change a selection (more on that below) by dragging it around. 

### Text Selection
There are a few ways to select text.  

- You can "double tap" on a word to select it.

- You can "triple tap" on a word to select the entire line.

- When you tap on the text, Flexile will display a menu under/over the cursor. That menu will have a "Select" and "Select All". "Select" will select the word the cursor is on. "Select All" will select all of the text.

- You can actually "Pinch" on the text field to select text. Flexile will select the text contained between the two fingers you're pinching with. This is probably more useful in the Note field, but it can be useful to easily select an entire text field without having to use the Tap->Menu->"Select All" method.

Once you've selected a bit of text you may notice that the end points of the selection contain braces.  You can, of course, drag those braces around.  However, you don't need to worry about trying to drag directly on the brace (those braces could be hard to hit if the text font is small).  Instead, you can drag anywhere  in the text field to change the selection.  Flexile will move the closest selection end point to where your finger is dragging.

After you've selected text (or changed a selection) you'll be presented with the following menu options: 

- Cut (deletes the selected text and copies it to the device clipboard)

- Copy (copies the text to the device clipboard)

- Select All (expands the selection to the entire text)

- Paste (is only presented if you have text in your clipboard). It replaces the selected text with whatever is in your clipboard.

- Delete (deletes the selected text)

Of course, you can also just start typing in the keyboard and whatever text you've selected will be replaced by whatever you're text your typing.

## Text Field
The Text Field is a simple, one-line field where you can enter text.

### Limitations 

- Text Fields are limited to 255 characters (this is a standard database limitation)

- Text Fields cannot have any "return" or "new line" characters. So any text you paste into the text field will be stripped of those characters.

### Options
- Auto Capitalization: You can choose to have Flexile automatically cap: Words, Sentences and All Characters. You can also turn this off (Select "None").

- Auto Correct: Yes, this is the infamous iOS auto-correct. You can turn this off by de-selecting this option for the field.

## Note Field
The note field is a simple text field that "wraps" text similar to the way a normal "text editor" would display text to fill the the space available.

### Options

- Auto Capitalization: You can choose to have Flexile automatically cap: Words, Sentences and All Characters. You can also turn this off (Select "None").
- Auto Correct: Yes, this is the infamous iOS auto-correct. You can turn this off by de-selecting this option for the field.

## Show & Hide Keyboard
At times you may see buttons on the toolbar like those shown in the image to the right.  You can use these to show or hide the keyboard.  This is most convenient with the Note field if you're wanting to read a large amount of text.  Essentially, it allow you to use the whole screen to read.