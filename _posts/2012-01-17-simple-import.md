---
layout: page
title: Simple Import
category: [support, import]
---

This will describe how to match import data (the columns) to a single table. I won't be going over many of the options here (check out the Complex Import Match tutorial for details on all options). But you can get a quick rundown of how to match import columns to to Flexile's Tables and Fields to easily import data into a single table.

## Match Layout
The match screen is divided with approximately the top 1/4 of the screen devoted to the import screens and the rest of the screen displaying the matched Tables/Fields. When you first open this screen, there won't be a a table to match.

### Adding a Table
To add a table simply tap on the Add (Plus) button. Flexile will display a list of tables you can choose from. Tap on the table you want and that table will be displayed in the Importing Tables screen. And that's it. You can add more tables, but that's beyond the scope of this tutorial.

### Matching Import Columns
Matching an import column to a Field is as simple as dragging the column down to that field. When you do, you'll see options appear for "Duplicate Check" and "Overwrite", with "Overwrite" selected by default. For now, we'll leave these options alone(they're explained in the Complex Import Tutorial. Any columns that are matched to fields will be imported and, conversely, those not matched won't be imported. When you match a column, you'll notice that the column will change color. Any columns that are matched will change color to indicate they're matched, but you can reuse those columns elsewhere if you need to.

### Default Values
You'll also notice a field column called "Default Value". You can use this to set a default value for the import field. If you've matched a column to that field, the default value will only be used if there is no data to import. If that field hasn't been matched, then the default value will be used for every imported record.

## Save the Match
Once you've matched at least one field, you can save the match by tapping on the Save button at the top-right of the screen. This will take you back to the original screen you came from so that you can import the file.