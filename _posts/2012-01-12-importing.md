---
layout: page
title: Importing
category: [support]
---

Flexile allows you to import data from CSV (comma separated values), TSV (tab separated values) and from the local contact database on the device. The import process is quite sophisticated, allowing you to adapt the import file to a variety of needs. In many case, you can actually duplicate within Flexile an entire other database (including relational data) through the import process alone. Alternatively, it can be used for very simple Imports... it all depends on what you want to do. Because there's so much to the import process, I've broken the instructions into a set of "mini" tutorials to make it a little easier.

Warning: Always backup your data before you import. If the import fails or corrupts your data for some reason, you will really want to have a backup available.

## Obtaining the Import Data
You'll first want to get the import data. There are a few ways to do this ranging from directly grabbing the file from a remote service to opening a file in Flexile from another app. This tutorial will describe how to do this.

## File Options
Depending of the type of data you're importing, there may be a few options associated with importing that file. You can find a description of all the available options here.

## Matching
Matching the Import Columns to Flexile's Tables and Fields is probably the most involved of the import process. For this reason there are several tutorials associated with matching:

- Simple Matching - This will describe matching up an import data to a single Flexile Table. It will not go over most of the options, but will get you quickly setup for simple Imports.
- Complex Matching - This will go into much more detail and describe matching import data to multiple Tables, duplication detection, auto-link generation. It will describe all of the import options.
- Import Templates - Because the matching process can be very complex, you can save and load import templates. This will describe how to do this as well as describe how a template is used to match import data with Flexile's Tables and Fields.
## Importing
After you've obtained the import data, set all the file options (if any) and finally matched up the import columns to Flexile's Tables & Fields, all you have left to do is actually import the data. You'll be presented with an Import button. Tap on the button and Flexile will begin importing your data. You'll see a progress bar as Flexile process all the import data. How long the import takes will depend on how much data there is to import as well as what options you've set when you matched the import columns. While Flexile is importing data you will not be able to to leave this screen until Flexile is finished. Note that you can leave the Flexile app during the import process but this is not recommended. If Flexile gets shut down during the import process you could loose data.

## Import Behavior
This will explain exactly how Flexile performs the import. It can sometimes help to know exactly what Flexile is doing behind the scenes, especially if you're performing a complex import. If you want some more technical details into the import process, this is place to to find them.