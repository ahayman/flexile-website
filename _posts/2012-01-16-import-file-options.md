---
layout: page
title: Import File Options
category: [support, import]
---

Flexile has the ability to import both CSV (comma separated files) and TSV (tab separated files).  Data rows can be split up between tables, auto-generating links, and deduplicate data to maintain the relational nature of the originating data. 

## CSV / TSV Options
For CSV and TSV files, there are a couple options you should be aware of.

### First Row Headers
In a CSV file it's common to use the first row of the import for column headers. If you select this option, Flexile will use the first row as column headers. A corollary to this is that if you select this option, the first row will not be imported so you'll want to be careful or you might loose a little data. If this option is not selected then Flexile will simply label the columns with an index (Ex: Column0, Column1, Column2, etc).

There is a trick though. If the first row doesn't contain headers, it can be a little difficult to figure out what "Column5" was supposed to be. However, if you select "First Row Headers", the column headers will be the data from the first row. This can make it easier to to match your columns to Flexile's tables/fields. Just be sure you unselect "First Row Headers" before you start the import process or you'll loose the first row of data.

### Backslashes are Escapes
This will be selected by default. There are certain text characters that are "special" (used for controlling the import process) like the double-quote: ". The backslash character is used to indicate this this character is to be interpreted as normal text rather than as a control character. Using a backslash for this is pretty much standard, which is why it's selected by default. Normally you won't need to mess with this, but there may be cases where unselecting this option will be necessary to properly process the import. You might try unselecting this option if you're having problems importing.

### Encoding Options
The encoding options allow you to choose how the text is encoded (the binary data that represents the actual characters). Unicode is the most common encoding format and most consider it the standard. So in most cases you can let Flexile detect the file's encoding and everything will work fine.  However there is one notable exception to this:  Microsoft.

Microsoft encodes most text files as Windows CP 1252 (MS-ANSI), especially if you're exporting from Excel or Access. Their format is close enough to Unicode that Flexile will think it's importing Unicode.  However, certain characters are different and the import may fail or truncate if it encounters them.  In these cases, it's best to set the encoding exactly to what was exported.