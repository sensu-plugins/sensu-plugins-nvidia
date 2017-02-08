# Change Log
This project adheres to [Semantic Versioning](http://semver.org/).

This CHANGELOG follows the format listed at [Keep A Changelog](http://keepachangelog.com/)

## [Unreleased]
### Added
- added metrics for `utilization.gpu`, `utilization.memory` (in percent)
- added metric for `power.draw` (in Watt)
- support for Ruby 2.3 (@eheydrick)

### Changed
- make metrics multi GPU aware

### Removed
- Support for Ruby < 2.1 (@eheydrick)

## [0.0.2] - 2015-07-14
### Changed
- updated sensu-plugin gem to 1.2.0

## 0.0.1 - 2015-07-04
### Added
- initial release

[Unreleased]: https://github.com/sensu-plugins/sensu-plugins-nvidia/compare/0.0.2...HEAD
[0.0.2]: https://github.com/sensu-plugins/sensu-plugins-nvidia/compare/0.0.1...0.0.2
