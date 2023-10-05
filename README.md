# asdf-redis ![Build](https://github.com/smashedtoatoms/asdf-redis/workflows/Build/badge.svg?branch=master)

Redis plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Dependencies
_This requires [brew](http://brew.sh) if you're on a mac, or a debian flavored linux.  If you need it to work on something else, you'll likely need to modify the plugin._

1. You will need a compiler.
  * Mac
    1. ```gcc```
    1. Hit the ok button and it will install.  If it already has it, then you are good.
  * Ubuntu
    1. ```sudo apt-get install linux-headers-$(uname -r) build-essential```

## Install

```
asdf plugin-add redis https://github.com/smashedtoatoms/asdf-redis.git
```

## Try it out
1. Open up a terminal and run `redis-server`.  This will get it running on the standard port (6379)
1. Open another terminal and run `redis-cli`.   This will open the redis cli so you can manually set, get, and delete keys.  For example:
```sh
~ % redis-cli
127.0.0.1:6379> set someKey "boomdiggity"
OK
127.0.0.1:6379> get someKey
"boomdiggity"
```
As long as that initial terminal session is running, you should be able to use it on port 6379 on localhost.  Have fun!

## Gotchas
This is a bare bones install of redis.  It has no configuration setup, no restart setup, or anything else.  It's just the binaries.  Fortunately, the binaries are usually all you need for dev environments.

## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Redis.

When installing Redis using `asdf install`, you can pass custom configure options with the following env vars:

* `REDIS_CONFIGURE_OPTIONS` - use only your configure options
* `REDIS_EXTRA_CONFIGURE_OPTIONS` - append these configure options along with ones that this plugin already uses
* `REDIS_APPLY_PATCHES` - a list of files or URLs to apply patches to Redis

You may also apply custom patches before building with `REDIS_APPLY_PATCHES`. For example:

```shell
REDIS_APPLY_PATCHES=$'dir/1.patch\n2.patch\nhttp://example.com/3.patch' asdf install redis 7.0.12
REDIS_APPLY_PATCHES="https://patch-diff.githubusercontent.com/raw/redis/redis/pull/12601.diff" asdf install redis 7.0.12
```
