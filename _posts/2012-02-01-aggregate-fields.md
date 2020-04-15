---
layout: page
title: Aggregate Field
category: [field]
---

The aggregate field will combine the values of a particular field in linked records.  Aggregate fields are updated when any of the records they refer to are changed.  The aggregate field is also updated when links are added to or removed from the record.

Since aggregate fields can refer to other aggregate fields, updates are cascaded through all the linked records.  This ensures your aggregates are kept updated.  But it could also lead to possibly lead to cyclical references (Record A refers to Record B refers to Record A).  Flexile will attempt to determine when adding an aggregate would cause a cyclical reference and will exclude that field from the selection. 

## Field Options
There are a variety of field options for the aggregate fields. 

**Field Prefix** - Same as the number field, this will place up to a 4 letter prefix for the field.
**Aggregate Type** -  The aggregate type determines what kind of mathematical operation is performed on the field in question. 

- Sum Total - This will add all valued in the linked fields.
- Average - This will take the average of all values in the linked fields. 
- Minimum - This will take the lowest value of all values in the linked fields. 
- Maximum - This will take the largest value of all values in the linked fields. 
- Count - This will return the count of the records in the linked fields that have values.   
- Aggregate Field -  This will allow you to choose the Table and Field you want to aggregate.  You can aggregate most number-based fields: Number Fields, Ratings, Date-based fields, Calculated Fields and Aggregate Fields.  If you're trying to aggregate a Calculated or Aggregate field and it doesn't show up to select, this means Flexile has determined that using the field would result in a cyclical reference. 

Field Format - This will allow you to choose the format the result of the aggregation.  The default is number, but you can display the result as a Date, Time, Date & Time as well as a Rating.

Recalculate Aggregates?   - Selecting this option will cause Flexile to recalculate all of the record aggregates for this field.  Of course, this is only useful when you're changing a pre-existing field that already has aggregated records.  Just be aware, that recalculating a large number of records may take time.

Table Aggregate - This allows you to select an aggregate to display at the bottom of the record list. Aggregates are updated whenever the table changes and you're not limited to the aggregate you chose. You can tap on the aggregate when it's displayed to switch to another one.