Changelog
=========

This changelog mostly documents breaking changes and deprecations.
For a complete list of releases, see the [releases page][0].

[0]: https://github.com/treehouselabs/queue-bundle/releases


## v0.1.0

### Changes
* Added Symfony3 support
* Added support for retrying/delaying/dead-lettering messages
* Added configuration to specify the strategy which retries are handled with
* Added cache warmer to declare exchanges/queues
* Added configuration to automatically create dead letter exchanges
* Improved exception handling and graceful shutdowns in `queue:consume` command
* Added option to enable/disable auto_declare exchange/queue (default true)


### Breaking changes
* Updated required PHP version to 5.6
* Updated required Symfony version to 2.7 (LTS)
* Updated `treehouselabs/queue` dependency to `0.2.0`. See those [release notes](https://github.com/treehouselabs/queue-bundle/releases/tag/v0.2.0)
  for an overview of breaking changes.
* Renamed `tree_house.queue.event_listener.queue` to `tree_house.queue.event_listener.flush`
* Replaced `attempts` config in consumers with a more extended `retry` config:

  **Before:**
  ```yaml
  consumers:
    foo:
      attempts: 2
  ```

  **After:**
  ```yaml
  consumers:
    foo:
      retry: 2
  ```
* Removed `ConsumeEvent` class: it is now part of the Queue library


## v0.0.1

First alpha release
