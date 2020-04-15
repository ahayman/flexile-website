---
layout: page
title: Field Import Behavior
category: [support, import]
---

Let's talk about how Flexile imports values. Flexile will have specific behavior for importing values dependent on what format the import value is in and what field it's being imported into.

- Text Field / Email / Website - Texts field will import almost any value. However, if you're importing text into a text field, the field will only import text up to any new-line character it comes across. Anything after the new-line character will be discarded. Number fields will be converted to text. Email & Website fields will be treated pretty much the same. Flexile doesn't validate that that the value is, in fact, an email or website.
- Note Field - Note field will pretty much import any text or number value (stored as text).
- Number Field - Number fields can also take both text a number values. Of course, number values will be imported as is. Text values will be converted to number values. Warning: In version 1.0.6, Flexile may not recognize negative values if there is any sort of text prefix in the field (Ex: $, #, or any text). This has been fixed in later versions.
- Phone Number - Phone numbers can also handle both text and number values. The phone number field store the phone number as an integer value. If the value is either a text or number value, the field will strip the value of all non-numeric digits and store the resulting integer. For example, if the value is "123.4567", the value stored will be "1234567".
- Date / Time / Date & Time - Collectively the date fields will accept Text, Number and Date values. Note that at the moment, Date values are only received from the local Contact Database (because that's how it's provided, which is nice). At the moment, if the number is a value, it's interpreted as the number of seconds from January 1, 2001. Number values can include decimal values (fractions of a second), although Flexile doesn't display Time values in fractions of a second. If the value is a text value, Flexile will attempt to determine the date from the text by using Apple's own Data Detector. This can actually detect a wide variety of date formats, but in some cases it may fail if the date format is too complex. It actually has an easier time detecting "human readable" (Jan 3, 2013) date formats rather than machine-like formats (2013-01-03T18:45:33.0012-18:00)... just FYI.
- Checkbox - The checkbox field will take both text and number value. If the value is a number, the checkbox field will evaluate the number as False (unchecked) if the number is 0, or True (checked) if the number is any other value. If the value is text, then the checkbox field will test for a variety of values: true/false, yes/no, y/n, t/f, 1/0. If the text values don't match any of those values, then it is converted into a number value and evaluated as a number (0 = False, any other number = True).
- Rating - The rating field will accept both Number and Text value. In both cases it will take and store the integer value of the import value. Note that it will not "clip" the value to the current max value. So even if the Max value is 10, the field will store a value of 20. However, the display of the value (number of stars shown) will be clipped.
- Image - The Image field will only accept Images (which, at the moment, is only available from the local Contact database).
- Audio Recording - Sorry, but at the moment you can't import audio files.
- Location / Address - The location field can only accept Text values. It will store the text value as is. The next time you open the record/field, the Map Field will search for the imported value and try to determine it's location.
- Pick List - The Pick List field is kind of a special case. It will accept both Text and Number values. For each import value, the field will search and determine if that value already exists as a pick list item. If the item exists then the field value for that record will be set to that value. If the value doesn't exist, then the field will add it as a new Pick-List value. You'll want to be careful with this. If you import a file with 100 different values for this field, you'll end up with a Pick-List that has 100 different values... which is probably not what you want.
## The Import Process
This will describe exactly how Flexile processes each import row. I’ve written it out in “ordinary” language but it’s still a bit technical. However, it may help you to understand what’s going on “under the hood” if you’re trying to import something complex. A small note on my formatting: Each indentation or sub-list assumes the item is it indented under, has evaluated as true. Also if you see a For Each, this means that everything indented under it is being looped.

### For Each Import Table:
- If there are any "Duplicate Check" Fields selected, perform a search in the table for an existing record using all Fields with this selected. If multiple records match, the first one is used.
- If there is no duplicate record, a new one is created.
- *For Each* Matched Field or Default
    - First test if there is an import column, we also test if there was a duplicate matched on this field. If there is an import column and the import field was matched, we don't want to import this since the values are the same.This will prevent records that are entirely matched from an unnecessary save.
        - Grab the import value for this column and check if the value exists.
            - If the import value exists we pass the value to the field so that it can “Sanitize” the value. How the field “Sanitizes” the value is described in the above section “Field Import Behavior”.
            - Set the record value for the field to the sanitized value.
        - If the import value doesn't exist, we attempt to apply a default import value.
        - If there is no default import value, we apply the default field value to the record.
    - If there is no import column, we check to see if there is a default import value we can apply. If there is, we apply it to the record only if the record doesn't already have a value.
    - If there is no default import value, we apply the default field value to the record. Note that this value usually will only apply if the record is new. The only caveat to this is if the field is a Data/Time field and it's set to update when the Field is modified.
- If any record values have changed, or the “Import Empty” is selected, we save the record and add it to an Array of saved record’s we’re keeping for this import row so we can add links later.
### Add Links
Now that we’ve added all the records (and kept track of them), we need to Link together the records (if this has been specified).

*For Each* Record in Saved Records

- Check if this record needs to be linked to the other records.
    - For Each Record in Saved Records
        - Add a Link from the record in the previous loop to this record only if there isn’t already a Link to that record and the two records aren’t the same record (which will happen exactly once since we’re iterating through the same array).

And that’s it. This is pretty much the logic of what occurs for each import row. Hopefully it gives you some insight into how the import process works and maybe gives you a better idea of how to structure your import.