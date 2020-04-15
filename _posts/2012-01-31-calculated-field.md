---
layout: page
title: Calculated Field
category: [field]
---

The calculated field allows you to perform calculations on other fields.  Flexile uses a drag and drop interface with an active alert system for creating the calculation formulas.  This should make it very easy to develop the calculations (yay! no formula typing).  Formulas are updated whenever any of the fields they reference are updated.

## Creating the Formula
To create the formula, tap on the "Formula" button in the field's options.  You'll be presented with a new screen you can use to create the formula.

The formula creator is divided into three sections.  The top section, which takes most of the screen, is where you can create the formula.  The middle section (toward the bottom of the screen) is labelled "Operands & Functions" and contains the various mathematical operations you can perform in the formula.  Finally, the bottom section is labelled "Constants & Fields" and contains all the usable fields as well as a "Constant" field that'll allow you to manually enter in a numeric value as a constant to be used in the formula.

### Adding Elements
To add formula elements to the formula, you can either drag the element up into the formula field or tap on it and it will be added to the end of the formula. To drag an element, you must drag up on the element.  If you drag left or right, you'll end up scrolling the field instead of dragging the element.  If you're having trouble dragging, you can also tap & hold on the element to "grab" it and then drag.

### Rearranging & Removing Elements
You can also grab the formula elements in the formula and move them around. If there are more elements than can fit in the formula field, it will scroll.  So trying to grab an element may result in scrolling the field instead.  If you're having trouble, try grabbing in a horizontal  direction (left or right).  You can also tap and hold on an element to "grab" it first, so you can then move it around.

To remove an element, simply drag the element out of the formula field. 

You should be aware that if you drag up any formula element with parenthesis, you'll end up with two elements: the open and the close parens separately.  Also, if you try to remove an parenthesis element (either the open or the close paren) the matching paren will also be removed.

### Errors
While you're rearranging elements, you'll often probably see error bubble ( ! ) displayed at various places. These are errors in the formula that need to be corrected before you save the formula.  Tap on an exclamation point to get more information about the error and find out how to fix it.

### Operands & Functions
 - +, -, /, *  - These are the basic mathematical functions and do pretty much what you'd expect them to.  The plus symbol '+' will add two fields together.  The minus symbol '-' will subtract right field from the left field.  The division symbol '/' will divide the left field by the right field.  Finally the multiplication symbol '*' will multiply the two fields.
- ^  - This operand will raise the left field by the right field.  So, for instance, if your left field is 10 and your right field is a constant "2", then it will raise 10 by 2 (result: 100).
- % - This is the modulus operator.  It will divide the left field by the right field and return the remaining value.
- ( )  - Parenthesis can be used to effect the order of mathematical operations.  Normally, Flexile will use the standard order of operations (division & multiplication before addition & subtraction).  Any operations within a set of parenthesis will be performed before those outside the parenthesis.  And yes, you can nest parenthesis within each other. 
- AVG( ) - This will take the average of a list of elements in the parenthesis.  You cannot use operands in the list, but you can insert a set of parenthesis and use operands inside the nested parenthesis.
- MAX( ) -   This will take the maximum of a list of elements in the parenthesis. You cannot use operands in the list, but you can insert a set of parenthesis and use operands inside the nested parenthesis.
- MIN( ) -  This will take the minimum of a list of elements in the parenthesis. You cannot use operands in the list, but you can insert a set of parenthesis and use operands inside the nested parenthesis.
- ABS( ) - This will take the absolute value of the result of whatever operations are within the parenthesis.
- SQRT( ) - This will take the square root value of whatever operations are within the parenthesis.

### Constants & Fields
You will be presented with a list of fields you can use in the formula.  You can use Number fields, Date-based fields, other Calculated fields, Aggregation fields and Rating fields in the formula.  If you don't see an aggregated or calculation field available, this means that Flexile has detected that using the field will result in an cyclical reference.

Constant  - The first field in the list will be a "Constant" field you can use to add constant values in the formula.  When you drag the constant up to the field, a number pad will be presented so you can enter the constant value.

## Field Options
There are several options available for the calculated field.  Most of the options are the same as you get with the number field, so you can take a look at what those options here.  However, to use those options you have to have the Field Format set to "Number".

### Field Format
The field format determines what format the results of the formula are displayed in.  The default is a standard Number.  But you can also choose Date, Time, Date & Time and Rating format.  If you do choose a date-based field, the value will be displayed as a time duration. 