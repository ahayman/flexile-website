---
layout: page
title: Copy Field
category: [field]
---

While editing a field's options, you may notice a curious option called "Enable Copy". This is a unique option that will allow you to copy in a value from another table (or even the same table) field.  This can allow you to use another record (in the same table) as a template, or you can even setup another table that only contains templates you can use to add records to this table.

## Options
If you select the "Enable Copy" option, you'll notice that you no longer have the option to select a field type. When you're copying from another field, this field will take on the field type and options of the field your copying from.  So instead of the normal options, you'll get a single option to select the Field you want to copy from.

### Copy From
To select a field, tap on the "Copy From" button.  You'll first be presented with a list of tables to choose from.  After choosing a table, you'll be presented with a list of fields.  You may notice that not all your fields will show up.  Currently, only the following fields are supported to copy data from:

- Text
- Note
- Email
- Website
- Checkbox
- Rating
- Number
- Pick List
- Phone Number
- Date, Time, Date & Time
- Location
- Calculated
- Aggregate

After choosing a field, you'll see the Field & Table name listed as "<Field> in <Table>".  Also, a second button will show up called "Trigger". 

### Trigger
Trigger allows you to set up another field in the current table as a trigger to copy values in from.   When you tap on the "Trigger" button, you'll be presented with a list of valid fields you can use as a trigger.  Important: Flexile will only display fields that are copying in values from the same Table  as this field. If you don't see any fields listed, this is why.  After you've selected a field, it will be listed in the "Trigger" option as "Copy on <Field>".

So this is how "triggering" work.  When you copy a record value into a "trigger" field, Flexile will also copy in values from the record into the fields that have selected the "trigger" field (using the method above). This will allow you to copy over several fields (or all of them) from a single record in a single action.

## Copy Action
When a field can copy in a value, you'll see a "Copy" button to the right of that field in the Detail View.  You can use that button to copy a record value in to the field.  Tapping on it will open a list of records in the table you're copying from.  Simply select the record you want and the value will be copied in. 

You should notice that the "Copy" button has three different colors:

- Default - The default color is the color of the label (not shown in the image).  If the Copy button is the default color, it means that it does not have a "trigger" field, nor do any other fields use this field as a trigger.  When you copy a record value in from this field, only this field will copy a value from the record.

- Green  - A green copy button means that this field is using another field as a trigger.  You can still copy record into this field using the copy button, but if the trigger field copies in a value this field will also copy in it's field value from that record, which will replace its current value.

- Red  - A red copy button means that this is a "trigger" field, and other fields will copy values from the same record when you use this field to copy.  

As a brief example, you'll notice in the image that the "Ingredient" field has a red copy button.  By tapping on that button and selecting an ingredient (from another table), the "Ingredient" field copied in the "Brown Rice Farina Hot Cereal" value from the record.  Since this was a "trigger" field, the following fields also copied in values from the same record: "Ingredient Portion Size", "Calories", "Carbs", "Sugar", "Protein" and "Fiber".  This saved the extra work of having to copy values in individual for each of the six field... a real time saver.

### A quick note about Copying
Copy values from another field does exactly that: It copies the value.  If you go back into the original record and change the original field value, the copied value will not  change.  You'd have to re-copy from that record in order to update the copied value.  There is no link between the copied record and the original record.  If you're looking to create a link so that the "copied" value updates with the original, use the Reference Field instead.