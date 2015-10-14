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
chart (all time totals). Both plots are saved for clicks and for keypresses,
respectively.

It's very likely that long intervals aren't split correctly.

Filtering options of original `selfstats` continue to work.

Config
======

In  `~/.selfspy/simplification_rules.txt`, add rules of the form:

    ^\s*::\s*$ --> unknown
    ^(.+)::\s*$ --> \1
    ^(.+)::.*$ --> \1
    # ^(.+)::(\w+).*$ --> \1:\2
    ^Firefox::.*YouTube.*$ --> Browser (Youtube)
    ^Firefox::.*GitHub.*$ --> Browser (GitHub)
    ^Firefox::.*Google Search.*$ --> Browser (search)
    # ^.*Skype.*$ --> Skype
    # ^.*Zimbra.*$ --> Mail
    # ^.*\bmutt\b.*$ --> Mail
    # ^.*\bzsh\b.*$ --> shell

to keep descriptions in legends short and expressive.
Last matching rule (LHS) wins.
