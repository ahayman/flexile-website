---
layout: page
title: Complex Import
category: [support]
---

Here we'll go over the full import matching process. The process can be pretty complex, and if you're just looking to import a single file into a single table, you'll probably be better served by going through the Simple Import Match Tutorial.

## Match Layout
The match screen is divided with approximately the top 1/4 of the screen devoted to the import screens and the rest of the screen displaying the matched Tables/Fields. When you first open this screen, there won't be a table to match.

### Adding/Removing Tables
To add a table, simply tap on the "+" button in the middle right of the screen. You'll be presented with the list of tables for you to choose from. Once you select a table it'll be displayed in the Importing Tables screen. You can add as many tables as you'd like to the match, even multiple instances of the same table. When/if you add more than one table, you can switch between the tables by tapping on the Collection button (the button between the "-" and "+" buttons). Tapping on this button will zoom out the current table and allow you to swipe between all the tables you've added. You can also tap on the "-" button to remove the currently selected table. If you do remove a table that has matched import columns, those columns will be replaced back in the Import Columns grid.

## Multiple Tables
Flexile can take import data and split that data between tables. As mentioned above, you can add table by tapping on the "+" button next to Importing Tables. When you add multiple tables, Flexile will take the each import row and import that data into each table you add by either creating a new record or else using an existing record (if a duplicate is found). You can add as many tables as you'd like... literally. You can even add the same table multiple times. If you do add a table multiple times, you'll actually get several records for that table for each row of data you import... depending. This might be easier if I use an example: Contacts (again!).

So let's say you're importing a Contact Database (either as a CSV file or from the Local Contact Database...either is fine). As a simple example, let's say that the Contact data you're importing has the standard contact info (First Name, Last Name, etc) along with several Phone Number fields (Mobile Phone, Home Phone, Work Phone). This is very common for Contact databases. However, let's also assume that you have two separate Tables in Flexile to keep track of this information: "Contacts" and "Phone Numbers". Of course, you'll add the Contact table and match the appropriate import columns. However, you now have several phone number fields that need to be matched. You can accomplish this by adding the "Phone Numbers" table multiple times, matching each Import column to a separate instance of the "Phone Numbers" table. In addition, you can set default values for other fields in each instance of the Phone Numbers table. So, for example, if you had a Pick List for the Phone type (Mobile, Home, Work, etc), you can set the default value to match the Import Column. Finally, if you check "Create Links" (explained below) on the "Contacts" table, every imported Contact Record will be Linked to the records created in Phone Numbers (per import row).

## Table Options
There are two options for each table: "Import Empty" and "Create Links"/"Links":

- Import Empty: Selecting this option will import a record for each import row regardless of whether there is import data or not. If this is not selected, Flexile will only create records if there is import data. As a small side note, if you don't select this option and you also don't match any import columns to the table....well, nothing will be imported into this table. Technically, you should be able to use this option to import a bunch of empty records, though I'm not entirely sure why you would want to do that. More likely, you'll want to set a Default Value and import a bunch of records with that value. I have seen situations where someone has set up a "calculations" table that is designed to only perform calculations on Links to other tables. In this case, there may be nothing to import, but you want a record created (and Linked to...more on that later) for each import row so that the calculations are automatically made. By using this, setting the appropriate default values and adding the "calculations" table multiple times, you can setup a set of calculations for each imported record.
- Create Links: If you select the "Create Links" (or "Links" on iPhone) Flexile will Link each imported record in this table to every other imported record per each imported row. In most cases, you'll only want to have one Table with this option selected. This is often a "Master" table of some sort that you want Linked to all the other tables. For instance, if you are importing Contact data, you might have a "Contacts" table along with several other tables for Phone Number, Email addresses, etc. In this case the "Contacts" table would have "Create Links" selected and Flexile would automatically Link each Imported Contact to all other imported table records for each respective import record. You wouldn't want to select "Create Links" in the "Phone Numbers" table though, since that would create Links between the Phone Numbers and Addresses, Email, etc..
## Matching Import Columns
To match up an import column with a table field, simple drag the column in question from the column grid down to the field you want to import the data into. If the table field is compatible with the import column, the table field will glow when you hover over it. If it doesn't glow, then the field is incompatible with the import column. In most cases the field will be compatible with the import column but there are some exceptions. For example, you can't drag an Image onto any field other than an image field. I know that's pretty obvious but I figured I should mention it.

When you drop an Import column onto a field it will arrange itself in the "Import Column" section of that field (assuming it's compatible). That import column is now matched and data in that column will be imported into the Table/Field. You'll also notice that the original import column displayed in the grid will turn a different color. This indicates that it's being used, which makes it easy to keep track of which Import Columns have been matched.

I should also mention that you can reuse import columns. So even if you've already matched an import column, you can still grab another copy of that Import Column and match it to a different Table/Field in the same way as you matched the first one. I'm not entirely sure why you would want to do this but hey, who am I limit your options?

You may also notice that once you match an import column to a field, additional options will show up for that field. I'll explain those next.

### Matched Field Options
Once you've matched an Import Column with a Field, you'll see two additional options show up:

- Duplicate Check: This option will be disabled by default. If you select this option, for each import row, Flexile will search through this current table and try to find a record that matches the Import value for the matched Import Column. It does this in conjunction with all other fields in the table that have this option selected. As an example, let's say you were importing from the Contact database (my favorite analogy) and you've matched the "First Name" and "Last Name", with both fields having selected "Duplicate Check". In that case, the import process would first search Flexile's Contact table for records that match the "First Name" and "Last Name" of each import. So yes, this means 500 records, Flexile would search the Contacts table 500 times. In most cases this will slow down the import process, but that's probably better than having a bunch of duplicate records.
- Overwrite: The overwrite option will be selected by default. When this option is selected, it will overwrite any existing data. Of course, if you deselect this option Flexile will only import data into this field if the record doesn't already contain data for the field. I'm sure you've figured this out, but this option really only works if you're using "Duplicate Check" in other fields. Otherwise, all the imported records will be new and there will never be anything to overwrite. You may also notice that if you select "Duplicate Check" on a field, the "Overwrite" option will disappear. This is done because if you're matching the import value to an existing value...well, the values will be the same so it's pointless to overwrite the existing value.
### Default Values
Each Table Field will have the option of setting a Default Value. Default Values are only used when there is no value to import. If you've matched an Import Column to the field, then the default value is only used when there is no import value for the specific row. However, if you've not matched an import column to the field, all imported records will have the default value set.

The exception to this is if no other field is matched to an import column. In that case the default value will not be used at all. You can override this behavior by selecting "Import Empty" for the table, in which case you'll have a bunch of records with only default values set.

#### Field Defaults
You may also recall that many fields can have a default value set internally (used when adding new records). The default value you set in the import process will override the standard field default. However, if no default is set and there's no importable value, then the field's standard default value will be used.

To recap, Flexile will import values in the following priorities (highest to least priority):

- Check if there is an import value. If there is, use it.
- Check there is no import value, use the Import Default if it's been set.
- If not Import Default has been set, use the Field Default if there is one.
- If there is no field default, no value will be created for the current record.

Exceptions You cannot set a default value for an Image field. Sorry about that. Sometime in the future I may be able to change this, but for right now it's not really feasible, and do really you actually want to?

## Imported Values
Let's talk about how Flexile imports values. Flexile will have specific behavior for importing values dependent on what format the import value is in and what field it's being imported into.

- Text Field / Email / Website - Texts field will import almost any value. However, if you're importing text into a text field, the field will only import text up to any new-line character it comes across. Anything after the new-line character will be discarded. Number fields will be converted to text. Email & Website fields will be treated pretty much the same. Flexile doesn't validate that that the value is, in fact, an email or website.
- Note Field - Note field will pretty much import any text or number value.
- Checkbox - The checkbox field will take both text and number value. If the value is a number, the checkbox field will evaluate the number as False (unchecked) if the number is 0, or True (checked) if the number is any other value. If the value is text, then the checkbox field will test for a variety of values: true/false, yes/no, y/n, t/f, 1/0. If the text values don't match any of those values, then it is converted into a number value and evaluated as a number (0 = False, any other number = True).