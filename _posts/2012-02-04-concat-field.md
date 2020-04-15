---
layout: page
title: Concatenation Field
category: [field]
---

The Concatenation field will allow you to take the text values from other fields and combine them into a single field according to a formula you create.  A simple example of this would be to take separate name fields (First, Middle & Last)  and combine them into a single field (Full Name).   Formulas can range from being fairly simple to remarkably complex, depending on how much control you want over the formatting of the text.

## Options
There's only one option for a Concatenation field: The Formula.  Tap on it to create a new formula or edit an existing formula.  If there is an existing formula, you'll see it displayed in the button. 

Warning: If you edit a formula, Flexile will recalculate the concatenation for every existing record in the table when you save the field.  If you have a lot of records, this may take a little while but Flexile will show you it's update progress.

## Formula
The concatenation formula can range from the very simple to complex formulas that insert formatting characters depending on the existence of field data.  To create the formula, you only need to drag and drop the fields you want into the formula and arrange them as makes sense to you.  

Tip:   You can also Tap on elements in the toolbars to add them to the end of the formula. 

Tip:  If you're having trouble "grabbing" an element to move it, Tap & Hold  on that element first until it turns "blue".

### Operands
There are three elements in the operands field you should know about: 

- Underscore (space) _ :  The underscore is an convenience operand for a "space". Simply drop it in where you want a space in your text. You could  add a space as a constant, but since spaces are such a common thing to insert into the formula, Flexile provides it as an easy "drop in".
- Parenthesis ( ) :    Parenthesis allow you to conditionally display a field along with constants. If the fields within a parenthesis don't have a value, then any constants/values also in the parenthesis will not be displayed.  This should help you sort out extra spaces and values between fields.  Nested parenthesis are dependent on their parents (outer parenthesis) to display their value.  This means if the out parenthesis has no field data, any inner parenthesis contained also won't display their data even if they have field data to display.  This will allow you create conditionals within your formula through nesting. 
- Curly Brackets { } :   Curly braces are similar to parenthesis in that they only display data if there is field data.  However, they will not display the field data itself.  Instead, they will only display the constants you've added into the curly braces.  The most common use for curly braces is to use them for control characters, like a comma between fields. Nested curly braces will not affect their parents (outer curly braces) in that if an inner curly brace has a field value, the outer curly brace will ignore that value unless it also has fields that qualify it to return a value.  This creates a logical 'AND' situation where field value must appear in both the outer and inner curly braces for values inside the inner curly braces to be part of the concatenation.

The Parenthesis and Curly Brackets allow you to create complex formatting dependent on field data. However, you don't have to use them. Sometimes all you want to do is create a simple formula.  Simply ignore the operands and add the values you want.

Fields
Most fields in your table will be available for concatenation.  Flexile will take the "text values" of those fields if they aren't intrinsically text fields. Date fields, for example, will be formatted into a full text date.  The one big exception is you can't concat other concatenation fields and you can't concat Note fields (seriously... why would you want to? ).   

Constant
The constant field is used to add to the text arbitrary strings (meaning: anything you want).  Simply drag (or tap) the field into the formula and a keyboard will pop up allowing you to enter the text you want.

ConcatWarning.png
Errors
As you drag elements in the formula around, you may notice red exclamation points appear ( ! ).  These are errors in the formula you must correct in order to save it.  Tap on the exclamation point to get more information about the error and how to fix it.