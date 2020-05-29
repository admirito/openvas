# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [7.0.1] (2020-05-12)

### Added
- Display gvm-libs version in `openvas --version` output [#436](https://github.com/greenbone/openvas/pull/436)
- Create greenbone-nvt-sync create lock file during feed sync.
  [#457](https://github.com/greenbone/openvas/pull/457)
  [#460](https://github.com/greenbone/openvas/pull/460)
- Extend script_get_preference() to get the value by id. [#471](https://github.com/greenbone/openvas/pull/471)

### Changed
- Improve handling of invalid or existent ids of nvt's preference id. [#416](https://github.com/greenbone/openvas/pull/416)
- Perform a scan even if there are missing plugins. [#439](https://github.com/greenbone/openvas/pull/439)
- Don't reload the plugins when start a new scan. [#457](https://github.com/greenbone/openvas/pull/457)
- Use new URL for GCF rsync. [#474](https://github.com/greenbone/openvas/pull/474)

### Fixed
- Do not store in memory an empty file received as nvt preference. [#409](https://github.com/greenbone/openvas/pull/409)
- Fix stop scan. [#414](https://github.com/greenbone/openvas/pull/414)
- Fix hanging scans. [#423](https://github.com/greenbone/openvas/pull/423)
- Improve signal handling when update vhosts list. [#426](https://github.com/greenbone/openvas/pull/426)
- Wait for all children instead of waiting just for one a time. [#429](https://github.com/greenbone/openvas/pull/429)
- Fix format-truncation warning in GCC 8.2 and later. [#462](https://github.com/greenbone/openvas/pull/462)

### Removed
- Drop HTTP sync [#489](https://github.com/greenbone/openvas/pull/489)

[7.0.1]: https://github.com/greenbone/openvas/compare/v7.0.1...v7.0.0

## [7.0.0] (2019-10-11)

### Added
- An ID has been added to NVT preferences. [#282](https://github.com/greenbone/openvas/pull/282)
- A new NVT cross references data handling has been added. [#317](https://github.com/greenbone/openvas/pull/317)
- Add option --scan-stop. [#352](https://github.com/greenbone/openvas/pull/352)
- Add support to open an rc4 stream cipher, the function to encrypt stream data using the cipher handle,
  and the function to close a handler. [#354](https://github.com/greenbone/openvas/pull/354)
- Add one single config for redis to config/redis-openvas.conf. [#370](https://github.com/greenbone/openvas/pull/370)

### Changes
- Vendor version is now an option in the config file. [#363](https://github.com/greenbone/openvas/pull/363)
- The NVT preference format has been changed. [#275](https://github.com/greenbone/openvas/pull/275)
- Redis supported versions must be 3.2 or higher. [#287](https://github.com/greenbone/openvas/pull/287)
- Log directory is now configurable. [#316](https://github.com/greenbone/openvas/pull/316)
- The greenbone-nvt-sync script is not allowed to run as root. [#323](https://github.com/greenbone/openvas/pull/323)
- OpenVAS Scanner has been renamed to OpenVAS (Open Vulnerability Assessment Scanner). [#337](https://github.com/greenbone/openvas/pull/337) [#343](https://github.com/greenbone/openvas/pull/343)
- Retry until a host finishes and frees a db before running a new host scan, in case there is no free redis db. Therefore a infinite loop has been added when it call kb_new(). [#340](https://github.com/greenbone/openvas/pull/340)
- Use new nvti_add_tag() instead of plug_set_tag() and remove plug_set_tag(). [#385](https://github.com/greenbone/openvas/pull/385)
- Remove dead code about tags regarding former openvas settings "result_prepend_tags" and "result_append_tags". [#386](https://github.com/greenbone/openvas/pull/386)
- Check cache/feed errors during plugin scheduling. [#358](https://github.com/greenbone/openvas/pull/358)
- Vendor version is now an option in the config file. [#363](https://github.com/greenbone/openvas/pull/363)
- Use API for accessing NVTI elements. [#365](https://github.com/greenbone/openvas/pull/365)

### Fixed
- An issue with stuck scans where only a single plugin is running and is beyond its timeout has been addressed. [#289](https://github.com/greenbone/openvas/pull/289)
- Fix a type mismatch. Use correct format specifier for size_t. [#299](https://github.com/greenbone/openvas/pull/299)
- An issue which caused falling back into a default port in get_ssh_port() has been fixed. [#342](https://github.com/greenbone/openvas/pull/342)
- An issue which could have caused a truncated string in register_service() has been fixed. [#373](https://github.com/greenbone/openvas/pull/373)
- Reset redis connection after the host scan finished. This avoids to leave open fd, which cause ulimit problems. [#384](https://github.com/greenbone/openvas/pull/384)
- Fix mis-identification of Sphinx Search service. [#387](https://github.com/greenbone/openvas/pull/387)
- Set a key in redis when the scan finishes and fix stop scan using the right pid. [#390](https://github.com/greenbone/openvas/pull/390)
- Fix detection of finger service. [#391](https://github.com/greenbone/openvas/pull/391)
- Wait for zombie process in case of timed out nvts. [#379](https://github.com/greenbone/openvas/pull/379)
- Fix handling of file type nvt preferences. [#399](https://github.com/greenbone/openvas/pull/399)

### Removed
- Unused be_nice scan preferences has been removed. [#313](https://github.com/greenbone/openvas/pull/313)
- OTP has been entirely removed in favor of using the ospd-openvas interface. [#333](https://github.com/greenbone/openvas/pull/333) [#351](https://github.com/greenbone/openvas/pull/351)
  [#337](https://github.com/greenbone/openvas/pull/337) [#389](https://github.com/greenbone/openvas/pull/389)
- Daemon mode has been entirely removed. [#337](https://github.com/greenbone/openvas/pull/337) [#341](https://github.com/greenbone/openvas/pull/341)

[7.0.0]: https://github.com/greenbone/openvas/compare/v6.0.1...v7.0.0

## [6.0.2] (unreleased)

### Changes
- The call to wmiexec.py has been replaced with impacket-wmiexec, because the symlink has been added in Debian Stretch with python-impacket 0.9.15-1.

[6.0.2]: https://github.com/greenbone/openvas/compare/v6.0.1...openvas-scanner-6.0

## [6.0.1] (2019-07-17)

### Added

### Changes
- Use lowercase for values added from add_host_name(). [#306](https://github.com/greenbone/openvas/pull/306)
- Do not launch the scan if the nvticache is corrupted. [#309](https://github.com/greenbone/openvas/pull/310)
- Separate each scan plugin process into its own process group. [#325](https://github.com/greenbone/openvas/pull/325)

### Fixed
- An issue which caused the scanner to crash when a plugin is missing during a scan has been addressed. [#296](https://github.com/greenbone/openvas/pull/296)
- An issue which causes a scan to hang has been addressed. [#301](https://github.com/greenbone/openvas/pull/301)
- Issues in building process have been addressed. [#308](https://github.com/greenbone/openvas/pull/308)
- An issue which caused resuming task not to work was addressed. [#312](https://github.com/greenbone/openvas/pull/312)
- An issue which caused a possible null IP values in OTP results / HOST_END has been addressed. [#321](https://github.com/greenbone/openvas/pull/321)
- An issue which caused the scanner to finish instantly without any result has been addressed. [#330](https://github.com/greenbone/openvas/pull/330)

### Removed
- Currently unused advanced_log related code has been removed. [#327](https://github.com/greenbone/openvas/pull/327)

[6.0.1]: https://github.com/greenbone/openvas/compare/v6.0.0...openvas-scanner-6.0

## [6.0.0] (2019-04-05)

### Added
- Function to get the currently running script filename has been added.

### Changed
- Debugging nasl mechanism has been improved, replacing preprocessor directives
  with g_debug facility.
- Code related to redis queries was improved.
- OpenVAS reload has been improved.
- Documentation has been improved.

### Fixed
- An issue related to the log facility and greenbone-nvt-sync has been fixed.
- An issue which caused nasl-lint to fail in case of unneeded nested functions has been addressed.
- An issue which caused returning erroneous values by get_plugin_preference() has been addressed.
- An issue which cause stuck scans where only a single plugin is running and is beyond its timeout has been addressed.
- Issues reported by static code analysis have been addressed.
- Issues in building process have been addressed.
- Several code improvements and clean-ups have been done.

### Removed
- Unused internal_send/recv() functions have been removed.

[6.0.0]: https://github.com/greenbone/openvas/compare/v6.0+beta2...v6.0.0
