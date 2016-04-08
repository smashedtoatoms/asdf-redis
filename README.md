# asdf-redis

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

## Gotchas
This is a bare bones install of redis.  It has no configuration setup, no restart setup, or anything else.  It's just the binaries.  Fortunately, the binaries are usually all you need for dev environments.

## Use

Check [asdf](https://github.com/asdf-vm/asdf) readme for instructions on how to install & manage versions of Redis.

When installing Redis using `asdf install`, you can pass custom configure options with the following env vars:

* `REDIS_CONFIGURE_OPTIONS` - use only your configure options
* `REDIS_EXTRA_CONFIGURE_OPTIONS` - append these configure options along with ones that this plugin already uses
