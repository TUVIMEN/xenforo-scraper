# xenforo-scraper

A bash script for scraping xenforo forums in json.

## Requirements

 - [hgrep](https://github.com/TUVIMEN/hgrep)
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

## Supported forums examples
    
    https://forums.freddyshouse.com/
    https://www.ignboards.com/
    https://www.cyclechat.net/
    https://zroadster.org/
    https://www.urban75.net/forums/

## Supported old forums examples

    https://forums.whyweprotest.net/
    https://www.forumhouse.ru/forums
    https://www.bigsoccer.com/forums/

## Usage

    xenforo-scraper [URL]...

Script downloads pages of threads and users and writes them in files. Files are named by their id's, but user files start with 'm-'. Old format forums don't create user files.

Download forum into current directory using 4 processes

    xenforo-scraper -p 4 'https://forum.com/forums/name.19/'

Download thread by irregular thread url into DIR 

    xenforo-scraper -d DIR -t 'https://forum.com/abcdef/loop/'

Download old format forum

    xenforo-scraper -o 'https://forum.com/forums/jus.82/'

Download whole forum

    xenforo-scraper -c 'https://forum.com/forums/'

Get some help

    xenforo-scraper -h
