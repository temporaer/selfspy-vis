# Visualization for selfspy
## Installation
Install [selfspy](https://github.com/gurgeh/selfspy), then the requirements with

    pip install -r requirements.txt

## Usage
The script is a modified version of the [`selfstats` program](https://github.com/gurgeh/selfspy#example-statistics).
The same options apply. Try e.g.

    python vis.py

## Status
Currently implemented is a breakdown of hours (stacked bar chart) and a pie
chart (all time totals). Both plots are saved for clicks and for keypresses,
respectively.

It's very likely that long intervals aren't split correctly.

Filtering options of original `selfstats` continue to work.

----

## Examples
For example, run

    selfvis.py --human-readable --pactive
    selfvis.py --human-readable --ratios

### Clicks
![Clicks Hours](clicks-hours.png)

![Clicks Total](clicks-total.png)

### Keystrokes
![Keystrokes Hours](keystrokes-hours.png)

![Keystrokes Total](keystrokes-total.png)

### Processes
> Not yet.

----

## Config
In  `~/.selfspy/simplification_rules.txt`, add rules of the form
``regexp --> name``

For examples:

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

See [this example](./simplification_rules.txt) for the rules I like.

----

## FAQ
#### *Is it supposed to be that slow?*
> Yup, don't expect your graphs to be produced in two seconds, it can take upto 15 seconds.

#### *Can I ...?*
> Yes, as long as you respect [the terms of the GPLv3 License](./LICENSE).

----

## About
### Authors?
- Original author: [Hannes Schulz (temporaer)](https://github.com/temporaer/selfspy-vis),
- Forked by: [Lilian Besson (Naereen)](https://github.com/Naereen/).

### License?
[GPL v3](./LICENSE).
