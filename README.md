# Archive

Any further development has been transfered to [forumscraper](https://github.com/TUVIMEN/forumscraper).

# xenforo-scraper

A bash script for scraping xenforo forums in json.

## Requirements

 - [reliq](https://github.com/TUVIMEN/reliq)
 - [jq](https://github.com/stedolan/jq)

## Installation

    install -m 755 xenforo-scraper /usr/bin

## Supported links formats

    http(s)?://forum.com/threads/.*
    http(s)?://forum.com/forum(s)?/threads/.*
    http(s)?://forum.com/.*/threads/.*
    http(s)?://forum.com/forums/.*
    http(s)?://forum.com/forum(s)?/forums/.*
    http(s)?://forum.com/.*/forums/.*
    http(s)?://forum.com/tags/.*
    http(s)?://forum.com/.*/tags/.*

## Json format

Here's example of [thread](thread-example.json), [old-thread](old-thread-example.json) and [user](user-example.json).

## Supported 2.x forums examples

    https://forums.freddyshouse.com/
    https://www.ignboards.com/
    https://www.cyclechat.net/
    https://zroadster.org/
    https://www.urban75.net/forums/
    https://www.1911forum.com/forums/
    https://www.ascentforums.com/
    https://www.alfaowner.com/forums/
    https://www.horseforum.com/forums/
    https://www.gunboards.com/forums/
    https://www.mothering.com/forums/
    https://forum-mechanika.pl/
    https://www.aclassclub.co.uk/forums/
    https://forum.literotica.com/
    https://forums.mangadex.org/
    https://www.mazda6club.com/forums/
    https://www.metaldetectingforum.com/index.php

## Supported 1.x forums examples

    https://www.bigsoccer.com/forums/
    https://www.forumhouse.ru/forums
    https://forums.whyweprotest.net/

## Usage

    xenforo-scraper [URL]...

Script downloads pages of threads and users and writes them in files. Files are named by their id's, but user files start with 'm-'. For 1.x forums script doesn't create user files.

By default script assumes 2.x version, for using 1.x version one must specify -o flags, as it is an old format.

Download forum into current directory using 4 processes

    xenforo-scraper -p 4 'https://forum.com/forums/name.19/'

Download thread by irregular thread url into DIR

    xenforo-scraper -d DIR -t 'https://forum.com/abcdef/loop/'

Download old format, 1.x forum

    xenforo-scraper -o 'https://forum.com/forums/jus.82/'

Download whole forum

    xenforo-scraper -c 'https://forum.com/forums/'

Get some help

    xenforo-scraper -h
