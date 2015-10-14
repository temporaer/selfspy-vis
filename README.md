Installation
============

Install selfspy, then

    pip install -r requirements.txt

Usage
=====

The script is a modified version of the `selfstats` program. The same options
apply. Try e.g.

    python vis.py

Status
======

Currently implemented is a breakdown of hours (stacked bar chart) and a pie
chart (all time totals). Both plots are shown for clicks and for keypresses.

It's very likely that long intervals aren't split correctly.

Filtering options of original `selfstats` continue to work.

Saving of plots is not yet implemented.

Config
======

In  `~/.selfspy/simplification_rules.txt`, add rules of the form:

    ^.*Vimperator.*$ --> Browser
    selfspy : \w+ --> selfspy
    ^.*Skype.*$ --> Skype
    ^.*Zimbra.*$ --> Mail
    ^.*\bmutt\b.*$ --> Mail
    ^.*\bzsh\b.*$ --> shell
    ^.*/([\w\-]+\.\w+) \[([\w\-]+)\] --> \2 : \1

to keep descriptions in legends short.
