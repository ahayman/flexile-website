---
layout: page
title: Running Balance Field
category: [field]
---

The running balance field is used to create a running balance on another field in the same table.  Unlike every other field, Flexile doesn't store running balance calculation in the table.  Instead, it calculates the balance when the record is displayed in the record list and updates those balances whenever the record set changes.  If you open a record from the record list, the detail view will also display the balance.

## Options
The running balance has a few options, most of them devoted to formatting the field.

- Field Prefix: Displays a prefix (up to 3 characters).  It's most often used for Currency symbols, but you can put anything you want in there (lb, kg, etc).
- Round Decimal: This determines how many decimals places the field will be rounded to.
- Digit Grouping: This determines how characters are included for digit grouping.  For example, the number 10000 is formatted as 10,000 with a digit grouping of 3 while it would be formatted as 1,00,00 with a digit grouping of 2.
- Select Field:   Tap this button to select the other field you want to create a running balance from.  Of course, you'll have to select a field in order to have a running balance.