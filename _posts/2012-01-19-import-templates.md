---
layout: page
title: Import Templates
category: [support, import]
---

Matching up the import columns to Flexile's tables/fields can be a very involved process and take quite a bit of time to setup. Because of this, it can be very frustrating to have to re-setup the import configuration of a complex import. To solve this, Flexile provides a method to save an import configuration as a template. This tutorial will explain how to use templates and describe how Flexile will use a template to match columns with fields (this is important...you should read it so you know what to expect).

## Accessing Templates
Templates can be accessed from the Match Screen, which will have a template button you can use to add/remove/select import templates. When you do (...or if you do) you'll see a List Editing Screen. This is the standard screen used for managing lists of... well, whatever (lots of things).

### Adding Templates
Adding a template requires you set up the match (configure the import) first. When you tap on the Add button, you will (per usual) be given a text box to name the template. After naming the template the current configuration will be saved under that template name.

### Selecting Templates
To select a template simply tap on it. That's it. Now, what happens after that is Flexile will attempt to apply that template to the current import file. I'll explain that a little later (below) but for now just realize that whatever configuration you had in the matcher will be overwritten by the template you selected.

### Editing Templates
You can only edit a template's name. To do this, simply tap on the Edit button and then tap on the template you want to select. Unfortunately, you can't actually edit the template yourself. Although you can apply (or select) a template, edit the configuration and add the edited configuration as a new template (and delete the old one if you don't want it).

### Deleting Templates
To delete a template, simply swipe right on that template and tap on the Delete button. You can also tap on the Edit button, then tap on the "-", button and then tap on the Delete button.

## Applying Templates
When you select a template, Flexile will attempt to apply that template to the current import file. It does so in a very specific manner:

- It attempts to match each matched import column to the current import column by using the column names. If it can find a column name in the current column set that matches the import column it uses the import column. Otherwise, it will discard the import column. However, this does mean that you can apply a template to different types of import files
- It will then attempt to find the Table & Field the column is matched to. Instead of using the Table/Field Name(s) it will use an Internal ID number. This means you can change the name of a Table (or Field) without worrying about breaking compatibility with the import template.
- If the template can match the Import Column (by column name) and the Table & Field (by ID), then it will apply that Match.
- Flexile will attempt to apply as many Template Import Columns as possible. Just be aware that it may not be able to match all fields if the import column names don't match or if you've removed Tables/Fields. Columns that aren't matched simply won't be used.

Warning: There's something you should know about how Flexile handles Fields. If you delete a field, Flexile will retain that Field for use later. I won't go into any details, but suffice it to say that there's a limitation in the way that Fields are stored that prevent them from being deleted. This means if you delete a Field and then later add a new one, the old Field space will but used. The ramifications are that it's possible for a Template to match an Import Column to a Table/Field that you don't intend. Moral of the story: *Double check the template.*