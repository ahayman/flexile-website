---
layout: page
title: Date Field
category: [field]
---

The date fields include 3 different fields: 

- Date
- Time
- Date & Time

Mostly, the field will work as you might expect it to.  The date format depends on the view it's displayed in, allowing you to display the field differently depending on where it shows up.  This can be useful if you want a short format style for lists, but prefer seeing a fuller style in detail (for more info see the Views tutorial). 

Note: In this tutorial I use the term "Date" to refer to both/either Date & Time.

## Options
The date field as an option for automatic updating.  You can use this to not only set default values for new records, but you can also have the date automatically update whenever the record is saved. 

### Update on Modified
Choosing this options will cause Flexile to automatically update the field when the record is modified.  You can override this in the record by setting a different date.  This means if you manually change the date in the record, Flexile will use that date rather than the current date when saving.  If you exit and re-enter the record, Flexile will then operate normally using the current date when you save the record.

### Update on Created & Update On Create + <time interval>
These options will automatically insert a date value when the record is created.  You should be aware that the value inserted is the current date when the record was created, not  when the record is saved (unlike "Update on Modified").  If you choose the option "Update on Created", the date inserted will be the current date.  However, you can also choose a variety of "future date" options, which will take the current time and add a time interval to it (1 hr, 1 day, etc).

These defaults are only inserted once, when the record is created.  So subsequent changes to the record will not result in an update to the field... unless, of course, you manually change the date.

## Data Entry
For some odd reason, I don't really think a bunch of spinning dials is a great way to enter a date, so I made a custom control that is a little more intuitive and reflects what most people expect to see when entering a date. 

Before we look at the controls, you should be aware of the extra buttons that the date field uses on the toolbar (shown right).

- Now -  This button does what it sounds like: it sets the date to the current date.
- Time / Calendar Icons  - If you're using the Date & Time field, this button will allow you to switch between the Calendar Control and the Time Control.  If you're using the Date Field or the Time Field, this button won't show up.
- Trash Icon  - Yep, it clears the date.  

### Calendar Control
The calendar control allows you to input a date (as in, day-month-year). You will hopefully notice that this control lays out the days of the month like a normal calendar.  

- Selecting a Year - There are buttons next to the listed year (top-left) that will allow you to change the year.  To be honest though, those buttons could be a bit hard to hit, especially on the iPhone.  Instead, you can actually swipe up/down on the calendar to change the year. Swiping Down will decrease the year by 1 and Swiping Up will increase the year by one.

- Selecting A Month - Similar to changing the Year, you can also use the buttons next to the list month (top-center) to change the month, but of course that could be frustrating.  Instead, you can Swipe Left to increase the month by 1 and Swipe Right to decrease the month by one.

- Selecting the Day  - Tap on it. :-)

### Time Control
The time control allows you to select a specific time.  At first glance, the time control can seem a little busy (maybe slightly overwhelming). There's a lot going on here, but once you grow accustomed to the layout, I think you'll find it makes it easy and quick to select a time.... a lot better than managing spinning dials (yes, yes... I'm prejudiced, I know... I hate spinning dials). 

There are four sections to the time control: AM/PM, Hour, Minute & Second selection. 

- AM/PM  - Pretty obvious, this will allow you to select the part of the day.  At the moment, I don't support 24-hour time display. That'll probably change eventually, but I think it'll require a separate control. I haven't actually gotten any requests for it, so I'm leaving it the way it is for now. If you need 24-hour display, please let me know and I'll bump it up as a priority.

- Hour - Yep, tap to select the hour.

- Minute - You'll notice that the minute section is divided into two parts: One part for changing the 10-minute value and the other section for changing the 1-minute value.  This will allow you to selectively change each part separately.  

- Second - The second selection is exactly like the minute selection except that your changing the second portion of the time.  