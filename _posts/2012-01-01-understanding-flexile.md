---
layout: page
title: Understanding Flexile
category: [support]
---

Flexile is a fairly easy system to use.  However, there are a few concepts you need to wrap your head around before Flexile will make sense to you.  Generally speaking, if you understand what a "Table" is (computer speak... not what you eat on :) and you understand how "Fields" and "Records" relate to a Table, then you should be fine.  Otherwise, I recommend reading the explanation below to understand these terms.

## Tables

The easiest way to think of a table is to think of it as a spreadsheet…. well ok, spreadsheets aren't really sexy so if you find a better analogy use that, but until then thinking of a table as a kind of spreadsheet can be useful.  Of course, in a spreadsheet you have columns and rows arranged in a grid.  The most common use of spreadsheets is to use the columns to define data types (ex: Name, Address, Phone, etc) and then enter your data into each row.  A database table is similar to a spreadsheet in that we define a set of datatypes (columns) that we call "Fields".  So we're going to call the columns "Fields" and the rows we will call "Records".  Each column (Field) can contain only one type of data, like a Text Field or a Number or even an Image (there's lots of field types).  You add Records and input information into each of the columns (what we call "Fields").  Generally, you create tables for types of information you want to store, like Contacts, a Journal, Music Collection, Movies you've seen, etc.  The first screen in Flexile will show you your list of tables (or Grid for the iPad) grouped into Categories of your choosing.

## Fields

Fields (the "columns" in a spreadsheet) define the types of information you store in a table.  Each Field specifies only one data type and by adding a Field to a Flexile table, you increase the amount of data each record in that table can hold.  When you add/edit a record in a table, the fields you create for that table become the controls you use to edit the information in the record.  And that's just a complicated way of saying that creating fields is like setting up the columns in a spreadsheet.  There are quite a few types of fields you can use to enter data like: Text Fields, Note Fields, Number Fields, Email, Websites, etc.  Flexile also includes more advanced fields such as Image Fields, Audio Fields, Calculated Fields and even Aggregate Fields (combining values from other tables).  

## Records

A record (the "rows" in a spreadsheet) represents the actual data you store in your table.  A record could be a person in your Contacts, or a Journal Entry, a Movie you've seen, a Book you've read or any number of things.  Before you enter records, you'll have to create a table (the "spreadsheet") and add fields ("columns") to that table.  For each record you enter the data into the fields you created for the table.  As an example, if you're adding a person to a "Contacts" table you might enter a Name (Text Field), Birthday (Date Field) and maybe a Category (Pick List: Friend, Family, Acquaintance).

## Links

A Link represents a connection from one record to another.  If you're using an iPad, you'll see along with that record all the links associated with that record.  If you're using an iPhone you can see a Record's Links by tapping on the "Links" button to the right of the Record Title (top of screen).  Technically, you don't actually see the Link (there is no spoon….) but instead you see the Record that's been linked to, but because calling it a record in this instance would be immensely confusing we're sticking with "Link".  These Links will be grouped according to their respective tables and organized by…well, you.  Flexile makes it easy to organize your Links by simply dragging the Link to where you want it.  Links are designed to give more meaning to a record by associating that record with other records.  Links really are one of the defining features of Flexile and can become a very powerful part of your database if used well, and liberally. 

## Views

Views are ways of displaying your data in different formats.  A lot of database programs display data almost exactly like a spreadsheet, which is to say…not very sexy or fun.  This can be useful, but more times than not it makes more sense to arrange your data differently.  And by differently, I mean just about any way you want to display it.  For each View, you're given options to arrange your fields in landscape/portrait orientation for various formats: Detail, List and Link.  Moreover, you can set up multiple pages of data for each view format.

### Detail View

The detail view is kind of what it sounds like.  It's the largest of the views and the view used when you want to edit a record (or create a new one).  Per usual, you can define the view format for both Landscape and Portrait orientations.

### List View

The list view is when your records are displayed in a table.  You can adjust the row height to accommodate as much information or as little information as you need.  Well… sort of… there is a limit to how tall you make a field (about 1/4 of the screen height) but it should be sufficient for most cases.

### Link View

Almost exactly the same as the List View except it's designed for when displaying your data in a link.  The link view is primarily displayed along with the detail view.  Often you'll want to minimize the amount of information in this format mainly to keep from cluttering up your detail view (to make it easy to find links).  

### Record Headers 

Both the List and Link views can use Record Headers, which place the Field labels in a header at the top of the Record List (or Link list) instead of along side each field value.  Using Record Headers can allow you to fit a lot more information on the screen at one time.
