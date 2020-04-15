---
layout: page
title: Number Field
category: [field]
---

The number field is actually a very versatile field, allowing to use it in a variety of circumstances for everything from quantities and dollar values to units of measurement, etc.   Just as important as the field, we created a custom keyboard that doubles as an in-app calculator you can use for data entry.

## Number Options
- Field Prefix - The field prefix will place up to a 4 character string as a prefix to the value.  The prefix will show up to the left of the field.  (For example, the prefix 'lbs' was used in the example image to the right).
- Round Decimal - The round decimal allow you to specify how many digits you want this field to round to.  You can choose to round to anywhere from 0 digits (round whole numbers) to 20 digits.  The number field will default to 2-digit rounding.
- Digit Grouping - This option will allow you to set how many digits are grouped together.  For example, by default it will group digits into 3, so the number 10000 will be displayed as 10,000 (much more human readable).  If you choose '0', the digits will not be grouped.
- Default - This will allow you to set a default value for new records.  The default value will only be applied to new records.
- Table Aggregate - This allows you to choose a table aggregate to display at the bottom of the table in record lists.
 
## Data Entry
When you enter data into a number field, you may notice that the number pad isn't the normal iOS keypad.  Flexile allow you to perform calculations right in the field itself.  Flexile will even keep a "tape" of the calculations you're queuing up. 

- To start calculating, simply tap on one of the mathematical operators.  Whatever number is currently in the field will get placed in the "tape" above the field.
- You can continue to "push" new values into the tape by tapping on an operation (+, -, *, /). 
- When you're ready, tap on the equal sign "=" to perform the calculation. 
- Note: The plus/minus sign ( ± ) changes the sign of the value currently in the field.  
- Be aware that calculations do adhere to the standard mathematical order of operations.  Therefore, all multiplication and division will be performed before any addition or subtraction is.
- You delete numbers by pressing the delete button "⇍".  If there are no numbers in the field itself, the delete button will "pull" the last number from the tape and begin deleting it (character by character).
- The tape does scroll if you push more numbers than can be displayed. 

## Constraints
For those that are wondering, Flexile stores number in the 'double' format.  This means the max value Flexile can store is:

`1.7976931348623157e+308`

and the minimum value flexile can store is: 

`2.2250738585072014e-308`

Those are really large (or small) numbers, so most people won't ever need to worry about it.  However, you should know what the limitations are. 