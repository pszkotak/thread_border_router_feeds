# Openwrt thread_border_router_feeds 

## Description

This is the OpenWrt "thread_border_router_feeds" repository.
It contains software needed to create the Internet Gateway for the Thread Network.

## Usage

This feed is meant to be used with OpenWrt Build System.


Your feeds.conf.default (or feeds.conf) should contain a line like:
```
src-git thread_border_router_feeds https://github.com/pszkotak/thread_border_router_feeds.git
```
To install all its package definitions, run:
```
./scripts/feeds update thread_border_router_feeds
./scripts/feeds install -a -p thread_border_router_feeds
```
