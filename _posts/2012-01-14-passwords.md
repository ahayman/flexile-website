---
layout: page
title: Passwords
category: [support]
---

Flexile allows you to create passwords for both the entire app as well as individual tables. Passwords are fully encrypted (using b-crypt with 10 rounds of salt... for the curious), which means once you create your password virtually no-one will be able to access it. Even Flexile doesn't know what the original password is. When you unlock a table (or the app) with a password, Flexile compares the resulting hash (encrypted text) to the one created from the original password. All that to say: your passwords are safe. However, if you loose your password you've lost your data. I can't retrieve it. Note: Just because I can't retrieve it doesn't mean other won't be able to. Using a good password technique will go a long way toward protecting your data.

## Types
You can choose to use either a full alpha-numeric password or a number-only password.

- Alpha-numeric Password: This will allow you to user virtually any character in your password, which can greatly increase the security of your password. Flexile will use the standard iOS keyboard to enter this kind of password. This potentially allows you to create more secure passwords, but it's also a little more difficult to use.
- Numeric (Pin) Password: Numeric-only passwords will display a Number pad for password entry, which most people find a lot easier to use than the standard keyboard. Your password will be less secure than if you use a full alpha-numeric password (with special characters) though. You can mitigate this some by using arithmetic on the password. For example, by multiplying (or better yet dividing) two numbers together you can essentially have a longer password that can be entered with fewer keystrokes.

Note: Flexile does store a flag in the database indicating whether a password is numeric only. So if someone gets a hold of our database, they can tell if you used only numbers in the password, which would make it easier to crack the password.

## App Password
Flexile can be password protected so that you must enter a password before you can use Flexile. You've got two options for when the password is required.

- You can require the password only on startup, which means Flexile will only require the password when it's started. It won't require the password if you're jumping between Flexile and another app.
- Flexile can require the password every time you enter Flexile. This means if you close the app (hit the home button) and immediately re-open Flexile, you'd have to re-enter the password. This is a lot more secure and, frankly, a lot more annoying... especially if you were trying to copy data from another app.
## Table Passwords
Each table can have it's own password. You'll be required to enter the password for a locked table to edit it or to view any of it's contents. This also applies to Links, so if you've linked a record to a locked table's record, you won't be able to view it until the password has been entered.

### Auto Lock
After you've added a password to a table, you'll see an Auto Lock checkbox you can select. You'll have to enter the table password to change this option. When this is selected, Flexile will automatically lock the table whenever you leave the app. If you leave the app while viewing any of the table's data (a record or the record list) Flexile will exit out of those screens. This will make the table more secure, but will also make it difficult to copy data between Flexile and another app.

### Password Groups
You may notice after adding a password to a table, the Category/Section Header the table is in will also sport a lock icon. This icon is not only useful to determine if there are any locked tables in the category, but you can also tap on it to unlock the tables in the category. Doing so will bring up the Password Entry Screen which you can use to enter a password that will then be applied to each locked table in the group (unlocked tables will be left alone). Those tables that have a matching password to the one you entered will be unlocked. Because unlocked tables are left alone, you could theoretically sub-divide a group into smaller groups by simply assigning different passwords to different tables.

Warning: Since the passwords are encrypted, it may take several seconds to unlock a group with many tables in it. Flexile has to apply that password to every locked-table. So if the unlock process is taking too long, you may consider splitting the tables into other categories to make the process a little more manageable.