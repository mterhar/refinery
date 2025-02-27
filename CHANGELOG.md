# Refinery Changelog

## 2.1.0 2023-08-04

This is a minor release with several new features and bug fixes, and is recommended for all Refinery users. See [Release Notes](./RELEASE_NOTES.md) for a summary of changes.

## Features
- feat: Add darwin-arm64 to the list of binaries. (#829) | [Kent Quirk](https://github.com/kentquirk)
- feat: Allow setting throughput for the cluster. (#827) | [Kent Quirk](https://github.com/kentquirk)
- feat: Record the event that caused trace evaluation. (#828) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add `has-root-span` operator to rules. (#814) | [Kent Quirk](https://github.com/kentquirk)
- feat: Validate Collection memory config through adding `conflictsWith` validation.(#806) | [Mason Legere](https://github.com/MasonLegere)
- feat: add a field with the formula used to decide to activate stress relief (#805) | [Terra Field](https://github.com/RainOfTerra)

## Fixes
- fix: Change default ConfigReloadInterval, add jitter, fix docs (#823) | [Kent Quirk](https://github.com/kentquirk)
- fix: add missing metrics fields (#811) | [Kent Quirk](https://github.com/kentquirk)
- fix: live reload deadlock (#810) | [Kent Quirk](https://github.com/kentquirk)
- fix: location and content of sample_rate metric (#809) | [Kent Quirk](https://github.com/kentquirk)
- fix: Update metadata for bad envvar and regenerate (#800) | [Kent Quirk](https://github.com/kentquirk)

## Maintenance
- docs: Touch up readme (#832) | [Kent Quirk](https://github.com/kentquirk)
- maint: use Go v1.20 (#831) | [Kent Quirk](https://github.com/kentquirk)
- maint: convert hardcoded operators to constants (#813) | [Kent Quirk](https://github.com/kentquirk)
- maint: Bump dependencies (#821) | [Kent Quirk](https://github.com/kentquirk)
- docs: refinery_rules.md (#802) | [Terra Field](https://github.com/RainOfTerra)

## 2.0.2 2023-07-14

This is a patch release to address additional issues with Refinery 2.0.

## Fixes

- fix: Redis scan batch size increase (#794) | [Renning Bruns](https://github.com/nullren)
- fix: Don't inject real metrics if they're not enabled. (#795) | [Kent Quirk](https://github.com/kentquirk)

## Maintenance

- maint: Dont try to publish external PRs to ECR (#797) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- maint: replace slash with dash in branch name (#796) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- maint: Docker tagging updates (#791) | [Terra Field](https://github.com/RainOfTerra)


## 2.0.1 2023-07-11

This is a patch release to address several issues in the 2.0.0 release.
Most of them were related to the new validation and config conversion features.
Validation has now been extended to include validation of values specified in environment variables.

## Features

- feat: Extended validation of config files (#781) | [Kent Quirk](https://github.com/kentquirk)

## Fixes

- fix: Remove excess validation for api keys (#786) | [Kent Quirk](https://github.com/kentquirk)
- fix: Update validate logic to use MemorySize (#782) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Promote stress relief activation and deactivation logs to Warn (#784) | [Kent Quirk](https://github.com/kentquirk)
- fix: Correct peer management default value (#783) | [Kent Quirk](https://github.com/kentquirk)
- fix: Update file_config to honor GRPCServerParameters.Enabled (#771) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Fix adjustmentinterval conversions inside rules-based samples (#768) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Inject all metrics and config later (#780) | [Kent Quirk](https://github.com/kentquirk)
- fix: Add missing validation for LegacyMetrics APIKey (#774) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Add ability to handle k8s unit format (#778) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Move Unknown log level to zero position (#772) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Fix bugs with convert (#764) | [Tyler Helmuth](https://github.com/TylerHelmuth)

# Maintenance

- docs: General Improvements (#789) | [Mary J](https://github.com/mjingle)
- docs: Update docs to fix memory description (#785) | [Kent Quirk](https://github.com/kentquirk)
- maint: Update release notes (#779) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- maint(deps): bump github.com/klauspost/compress from 1.16.6 to 1.16.7 (#763)
- maint(deps): bump github.com/sirupsen/logrus from 1.9.2 to 1.9.3 (#761)
- maint(deps): bump google.golang.org/protobuf from 1.30.0 to 1.31.0 (#759)
- maint(deps): bump google.golang.org/grpc from 1.55.0 to 1.56.1 (#758)

## 2.0 2023-07-06


** NEW MAJOR VERSION **
!! BREAKING CHANGES !!
Configuration file formats have changed and some functionality has changed.
Use the new converter tool to convert existing configuration and rules files. Binaries are available as part of the release.
For more information, see [the release notes](https://github.com/honeycombio/refinery/blob/main/RELEASE_NOTES.md).

## Features

- feat: Rewrite config code without Viper (#654) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add Warn() to Logger interface (#656) | [Kent Quirk](https://github.com/kentquirk)
- feat: Config conversion and validation code from one data file (#677) | [Kent Quirk](https://github.com/kentquirk)
- feat: Refactoring of rules configuration and rules converter (#681) | [Kent Quirk](https://github.com/kentquirk)
- feat: Remove trace key params -> add meta sample_key (#685) | [Kent Quirk](https://github.com/kentquirk)
- feat: Use the new configuration system (#690) | [Kent Quirk](https://github.com/kentquirk)
- feat: Metrics cleanup (#692) | [Kent Quirk](https://github.com/kentquirk)
- feat: Validation integration, part 1 (#700) | [Kent Quirk](https://github.com/kentquirk)
- feat: More validation add rules metadata and rules validation (#701) | [Kent Quirk](https://github.com/kentquirk)
- feat: Integrate validation into the executable (#706) | [Kent Quirk](https://github.com/kentquirk)
- feat: Write out parsed configs (#707) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add EMAThroughput sampler support (#708) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add WindowedThroughput sampler (#709) | [Kent Quirk](https://github.com/kentquirk)
- feat: Support MaxKeys in configs and add default of 500 (#710) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add sampler metrics (#714) | [Kent Quirk](https://github.com/kentquirk)
- feat: Preregister libhoney metrics (#716) | [Kent Quirk](https://github.com/kentquirk)
- feat: Warn about samplers that might need adjustment (#718) | [Kent Quirk](https://github.com/kentquirk)
- feat: Allow suffixes on memory size in config (#719) | [Kent Quirk](https://github.com/kentquirk)
- feat: MaxAlloc improvements (#721) | [Kent Quirk](https://github.com/kentquirk)
- feat: Allow disabling reload monitoring (#730) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- feat: Add ability to convert a helm chart (#736) | [Kent Quirk](https://github.com/kentquirk)
- feat: Enable pyroscope deltaprof (#747) | [Liz Fong-Jones](https://github.com/lizthegrey)

## Fixes

- fix: Check apikeys for otlp requests too (+tests) (#672) | [Kent Quirk](https://github.com/kentquirk)
- fix: Various config fixes (#684) | [Kent Quirk](https://github.com/kentquirk)
- fix: Send a small amount of data to peers during stress relief (#688) | [Kent Quirk](https://github.com/kentquirk)
- fix: Add stress relief reason; fix JSON unmarshal bug (#698) | [Kent Quirk](https://github.com/kentquirk)
- fix: Log reason for MinimumStartupDuration (#703) | [Terra Field](https://github.com/RainOfTerra)
- fix: Rework APIKeys logic (#712) | [Kent Quirk](https://github.com/kentquirk)
- fix: Update dynamic samplers to count spans instead of traces (#717) | [Kent Quirk](https://github.com/kentquirk)
- fix: Try a few slots when there's a buffer overrun. (#722) | [Kent Quirk](https://github.com/kentquirk)
- fix: Make refinery run from minimal config (#724) | [Kent Quirk](https://github.com/kentquirk)
- fix: Correct dependency injection instability (#741) | [Kent Quirk](https://github.com/kentquirk)
- fix: Query auth bug fix; add tests (#753) | [Kent Quirk](https://github.com/kentquirk)
- fix: Improve drop cache performance (#757) | [Kent Quirk](https://github.com/kentquirk)

## Maintenance

- perf: preallocate outbound libhoney attribute map (#754) | [Liz Fong-Jones](https://github.com/lizthegrey)
- docs: Generated Refinery docs for docs site improvements (#752) | [Mary J](https://github.com/mjingle)
- docs: Update config_complete.yaml (#751) | [Kent Quirk](https://github.com/kentquirk)
- docs: Regenerate docs from recent changes (#750) | [Kent Quirk](https://github.com/kentquirk)
- docs: Update APIKeys reference in config (#748) | [Mary J](https://github.com/mjingle)
- maint: Update dynsampler-go to latest to fix bug (#746) | [Kent Quirk](https://github.com/kentquirk)
- docs: Fix up docs, especially envvar and cmdline (#737) | [Kent Quirk](https://github.com/kentquirk)
- docs: Fix convert help and docs (#744) | [Kent Quirk](https://github.com/kentquirk)
- maint: README updates -- round 1 (#742) | [Phillip Carter](https://github.com/cartermp)
- maint(deps): Bump github.com/klauspost/compress from 1.16.4 to 1.16.5 (#675) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): Bump github.com/prometheus/client_golang from 1.14.0 to 1.15.1 (#676) | [dependabot[bot]](https://github.com/dependabot[bot])
- refactor: Rename fields for clarity in an E&S world (#680) | [Kent Quirk](https://github.com/kentquirk)
- maint: Update dependencies (#699) | [Kent Quirk](https://github.com/kentquirk)
- docs: Improve generated documentation (#711) | [Kent Quirk](https://github.com/kentquirk)
- maint: Generate docs better suited to docs team prefs (#713) | [Kent Quirk](https://github.com/kentquirk)
- maint: Remove remaining references to obsolete fields (#720) | [Kent Quirk](https://github.com/kentquirk)
- docs: Refinery Rules copyediting (#731) | [Mary J](https://github.com/mjingle)
- ci: Update build_binaries to build convert (#732) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- docs: Add generator for website docs (#733) | [Kent Quirk](https://github.com/kentquirk)
- docs: Refinery Config copyediting (#734) | [Mary J](https://github.com/mjingle)
- chore: Switch to temp credentials for CI (#735) | [Nathan Lincoln](https://github.com/NLincoln)
- docs: Fix up docs, especially envvar and cmdline (#737) | [Kent Quirk](https://github.com/kentquirk)
- maint: Clarify 1.x configs for 1.x folks, remove old stuff (#739) | [Phillip Carter](https://github.com/cartermp)

## Additional contributions by:

- Documentation fix | [Kevan Carstensen](https://github.com/isnotajoke)
- WindowedThroughput sampler (in dynsamplers-go) | [Yi Zhao](https://github.com/yizzlez)

## 1.21.0 2023-04-14

### Summary
Adds many fixes for existing features such as meta fields for use with stress relief mode. Adds ability to annotate sample rates that
were already set upstream before refinery sampling for debugging purposes.

### Enhancements
- feat: annotate incoming sample rate (#658) | [Faith Chikwekwe](https://github.com/fchikwekwe)

### Bug Fixes
- fix: Replace incorrectly used Systemd Alias directive with a WantedBy (#657) | [Irving Popovetsky](https://github.com/IrvingPopovetsky)
- fix: add hostname to span during stress relief mode (#666) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- fix: only decorate late spans when configured to do so (#665) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- fix: validate cache overrun strategy for stress relief mode (#664) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- docs: update doc to remove deprecated field name (#659) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- fix: Remove Stop() function from stress relief (#645) | [Kent Quirk](https://github.com/kentquirk)
- chore: Spelling (#644) | [Josh Soref](https://github.com/JoshSoref)
- fix: tweak timeouts (#647) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- fix: correct syntax error in config_complete.toml (#639) | [Hazel Weakly](https://github.com/HazelWeakly)

### Maintenance
- chore: Update MetricsReportingInterval in config_complete.toml (#653) | [Davin](https://github.com/Davin)
- maint: switch dependabot to collection (#660) | [Vera Reynolds](https://github.com/Vera Reynolds)
- maint(deps): bump google.golang.org/protobuf from 1.28.1 to 1.30.0 (#663) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump github.com/honeycombio/husky from 0.21.0 to 0.22.2 (#662) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump github.com/klauspost/compress from 1.16.3 to 1.16.4 (#661) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump go.uber.org/automaxprocs from 1.5.1 to 1.5.2 (#650) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump github.com/honeycombio/dynsampler-go from 0.3.0 to 0.4.0 (#649) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump google.golang.org/grpc from 1.52.3 to 1.54.0 (#652) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump github.com/honeycombio/husky from 0.21.0 to 0.22.2 (#651) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint(deps): bump github.com/klauspost/compress from 1.16.0 to 1.16.3 (#648) | [dependabot[bot]](https://github.com/dependabot[bot])
- maint: Add labels to docker image (#640) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- maint: Add LICENSES dir (#638) | [Tyler Helmuth](https://github.com/TylerHelmuth)

## 1.20.0 2023-03-10

### Summary
This is a significant new release of Refinery, with several features designed to help when operating Refinery at scale:

For details on all of the new features, please see the [new Release Notes document](./RELEASE_NOTES.md)
New features must be enabled by adjusting configuration.

### Enhancements
- feat: Add configuration for trace and parent ID field names (#630) | [Davin Taddeo](https://github.com/tdarwin)
- feat: allow ability to add new attributes to refinery data (#621) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- feat: Add ability to set Redis database and prefix in config (#614) | [Kent Quirk](https://github.com/kentquirk)
- perf: Improve performance of stress relief (#604) | [Kent Quirk](https://github.com/kentquirk)
- feat: Stress Relief system (#594) | [Kent Quirk](https://github.com/kentquirk)
- feat: extend and unify metrics system (#593) | [Kent Quirk](https://github.com/kentquirk)
- feat: allow user to convert datatype if valid (#585) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- feat: Implement alternative sharding using rendezvous hash to improve dynamic scalability (#570) | [Kent Quirk](https://github.com/kentquirk)
- feat: On shutdown, remove ourself from the peers list (#569) | [Kent Quirk](https://github.com/kentquirk)
- feat: Add cuckoo-based drop cache (#567) | [Kent Quirk](https://github.com/kentquirk)
- feat: Extract Sent Cache to an interface for future expansion (#561) | [Kent Quirk](https://github.com/kentquirk)

### Bug fixes
- fix: do not send sample rate in dry run (#611) | [Faith Chikwekwe](https://github.com/fchikwekwe)
- fix: Remove API key logging (#606) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- fix: Fix flaky tests, clean up logic on rules (#596) | [Kent Quirk](https://github.com/kentquirk)
- fix: Add missing done channel to fix build (#573) | [Kent Quirk](https://github.com/kentquirk)

### Maintenance
- chore: publish should only happen on main (#627) | [Kent Quirk](https://github.com/kentquirk)
- chore: Publish every build to honeycomb's ecr (#613) | [Kent Quirk](https://github.com/kentquirk)
- docs: update FieldList (#591) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- docs: add environment variables (#589) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- chore: Update CODEOWNERS (#588) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- chore: Change workflow to use Collections board (#587) | [Kent Quirk](https://github.com/kentquirk)
- chore: update dependabot (#583) | [Kent Quirk](https://github.com/kentquirk)
- chore: update validate PR title workflow (#572) | [Purvi Kanal](https://github.com/pkanal)
- chore: validate PR title (#571) | [Purvi Kanal](https://github.com/pkanal)
- refactor: Change Router to use TraceServer (#607) | [Tyler Helmuth](https://github.com/TylerHelmuth)
- maint(deps): bump golang.org/x/net from 0.4.0 to 0.7.0 (#628) | dependabot[bot]
- maint(deps): bump github.com/pelletier/go-toml/v2 from 2.0.6 to 2.0.7 (#620) | dependabot[bot]
- maint(deps): bump github.com/honeycombio/husky from 0.19.0 to 0.21.0 (#619) | dependabot[bot]
- maint(deps): bump github.com/klauspost/compress from 1.15.15 to 1.16.0 (#618) | dependabot[bot]
- maint(deps): bump github.com/stretchr/testify from 1.8.1 to 1.8.2 (#616) | dependabot[bot]
- maint(deps): bump github.com/honeycombio/husky from 0.17.0 to 0.19.0 (#603) | dependabot[bot]
- maint(deps): bump github.com/hashicorp/golang-lru from 0.5.4 to 1.0.1 (#602) | dependabot[bot]
- maint(deps): bump github.com/klauspost/compress from 1.15.12 to 1.15.15 (#601) | dependabot[bot]
- maint(deps): bump github.com/honeycombio/dynsampler-go from 0.2.1 to 0.3.0 (#600) | dependabot[bot]
- maint(deps): bump grpc to 1.52.3 (#599) | [Kent Quirk](https://github.com/kentquirk)
- maint(deps): bump github.com/spf13/viper from 1.13.0 to 1.15.0 (#597) | dependabot[bot]
- maint(deps): Bump github.com/prometheus/client_golang from 1.13.0 to 1.14.0 (#576) | dependabot[bot]
- maint(deps): Bump github.com/tidwall/gjson from 1.14.3 to 1.14.4 (#575) | dependabot[bot]
- maint(deps): Bump github.com/hashicorp/golang-lru from 0.5.4 to 1.0.1 (#574) | dependabot[bot]

## 1.19.0 2022-11-09

Adds new query command to retrieve configuration metadata, and also allows for a new (optional) cache management strategy that should be more effective at preventing OOM crashes in situations where memory is under pressure.

### Enhancements

- Add command to query config metadata (#556) | [@kentquirk](https://github.com/kentquirk)
- New cache management strategy (#547) | [@kentquirk](https://github.com/kentquirk)

### Fixes

- Set content-type on marshalToFormat (#548) | [@kentquirk](https://github.com/kentquirk)

### Maintenance

- Bump google.golang.org/grpc from 1.50.0 to 1.50.1 (#553)
- Bump github.com/fsnotify/fsnotify from 1.5.4 to 1.6.0 (#552)
- Bump github.com/stretchr/testify from 1.8.0 to 1.8.1 (#551)
- Bump github.com/honeycombio/libhoney-go from 1.16.0 to 1.18.0 (#550)
- Bump github.com/klauspost/compress from 1.15.11 to 1.15.12 (#549)

## 1.18.0 2022-10-12

### Enhancements

- Track span count and optionally add it to root (#532) | [@kentquirk](https://github.com/kentquirk)
- Add support for metrics api key env var (#535) | [@TylerHelmuth](https://github.com/TylerHelmuth)

### Fixes

- RedisIdentifier now operates properly in more circumstances (#521) | [@Baliedge](https://github.com/Baliedge)
- Properly set metadata to values that will work. (#523) | [@kentquirk](https://github.com/kentquirk)

### Maintenance

- maint: add new project workflow (#537) | [@vreynolds](https://github.com/vreynolds)
- Bump go version to 1.19 (#534) | [@TylerHelmuth](https://github.com/TylerHelmuth)
- Bump github.com/klauspost/compress from 1.15.9 to 1.15.11 (#531)
- Bump github.com/honeycombio/husky from 0.15.0 to 0.16.1 (#529)
- Bump github.com/prometheus/client_golang from 1.12.2 to 1.13.0 (#528)
- Bump github.com/spf13/viper from 1.12.0 to 1.13.0 (#527)
- Bump Husky to v0.17.0 (#538) | [@kentquirk](https://github.com/kentquirk)

### New Contributors

- @Baliedge made their first contribution in https://github.com/honeycombio/refinery/pull/521
- @TylerHelmuth made their first contribution in https://github.com/honeycombio/refinery/pull/534

**Full Changelog**: https://github.com/honeycombio/refinery/compare/v1.17.0...v1.18.0

## 1.17.0 2022-09-16

### Enhancements

- Allow adding extra fields to error logs (#514) | [@kentquirk](https://github.com/kentquirk)
- Allow BatchTimeout to be overridden on the libhoney Transmission (#509) | [@leviwilson](https://github.com/leviwilson)

### Fixes

- Consolidate honeycomb metrics to use single lock & fix concurrent read/write (#511)| [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Fix variable shadowing bug (#519)| [@kentquirk](https://github.com/kentquirk)

## 1.16.0 2022-09-09

This release contains a number of small new features to assist in running refinery more effectively:

- Adds new endpoints to help in debugging refinery rules (see README.md)
- Fixes issues with SampleRate
- Adds some new configuration parameters (see the *_complete.toml files for more)
- Conforms to the GRPC standard for health probes
- Accepts OTLP/JSON traces and conforms to the most recent OTLP trace specification

### Enhancements

- Add /query endpoints to help debug refinery rules (#500, #502) | [kentquirk](https://github.com/kentquirk)
- Implement grpc-health-probe (#498) | [abatilo](https://github.com/abatilo)
- Make gRPC ServerParameters configurable (#499) | [abatilo](https://github.com/abatilo)
- Fix sample rate for late spans (#504) | [kentquirk](https://github.com/kentquirk)
- Optionally record why a sample decision was made (#503) | [kentquirk](https://github.com/kentquirk)
- Added PeerManagement.Timeout config option (#491) | [thrawn01](https://github.com/thrawn01)
- Add 'meta.refinery.original_sample_rate' (#508) | [epvanhouten](https://github.com/epvanhouten)

### Maintenance

- maint: improvements to GitHub operation (#474, #477, #478) | [JamieDanielson](https://github.com/JamieDanielson), [vreynolds](https://github.com/vreynolds)

### Dependencies

- Bump github.com/stretchr/testify from 1.7.2 to 1.8.0 (#472) | [dependabot](https://github.com/dependabot)
- Bump github.com/sirupsen/logrus from 1.8.1 to 1.9.0 (#484) | [dependabot](https://github.com/dependabot)
- Bump google.golang.org/grpc from 1.46.2 to 1.49.0 (#485, 494) | [dependabot](https://github.com/dependabot)
- Bump github.com/honeycombio/libhoney-go from 1.15.8 to 1.16.0 (#487) | [dependabot](https://github.com/dependabot)
- Bump github.com/gomodule/redigo from 1.8.8 to 1.8.9 (#488) | [dependabot](https://github.com/dependabot)
- Bump github.com/klauspost/compress from 1.15.7 to 1.15.9 (#495) | [dependabot](https://github.com/dependabot)
- Bump github.com/tidwall/gjson from 1.14.1 to 1.14.3 (#497) | [dependabot](https://github.com/dependabot)
- Update github.com/honeycombio/husky to latest and fix breaking changes (#505) | [kentquirk](https://github.com/kentquirk)
- Go mod tidy (#507) | [kentquirk](https://github.com/kentquirk)

## New Contributors

- @abatilo made their first contribution in https://github.com/honeycombio/refinery/pull/498
- @thrawn01 made their first contribution in https://github.com/honeycombio/refinery/pull/491
- @epvanhouten made their first contribution in https://github.com/honeycombio/refinery/pull/508

**Full Changelog**: https://github.com/honeycombio/refinery/compare/v1.15.0...v1.16.0

## 1.15.0 2022-07-01

### Enhancements

- Add rule Scope configuration option to rules-based sampler (#440) | [isnotajoke](https://github.com/isnotajoke)
- Replace hand-rolled binary.BigEndian.Uint32 with the real deal (#459) | [toshok](https://github.com/toshok)
- Validate successful span scoped rules test (#465) | [MikeGoldsmith](https://github.com/MikeGoldsmith)
- Create helm-chart issue on release (#458) | [MikeGoldsmith](https://github.com/MikeGoldsmith)
- github_token needs underscore not hyphen (#464) | [@JamieDanielson](https://github.com/JamieDanielson)

### Maintenance

- Replace legacy with classic in readme (#457) | [MikeGoldsmith](https://github.com/MikeGoldsmith)

### Dependencies

- Bump github.com/spf13/viper from 1.10.1 to 1.12.0 (#461)
- Bump github.com/stretchr/testify from 1.7.1 to 1.7.2 (#467)
- Bump github.com/honeycombio/husky from 0.10.5 to 0.10.6 (#460)
- Bump github.com/klauspost/compress from 1.15.4 to 1.15.6 (#466)
- Bump github.com/prometheus/client_golang from 1.12.1 to 1.12.2 (#463)

## 1.14.1 2022-05-16

### Fixes

- Fix crash bug related to sharding (#455) | [@kentquirk](https://github.com/kentquirk)

### Maintenance

- bump husky to 0.10.5 (#450) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Bump github.com/klauspost/compress from 1.15.2 to 1.15.4 (#451) | dependabot
- Bump github.com/tidwall/gjson from 1.14.0 to 1.14.1 (#444) | dependabot
- Bump github.com/fsnotify/fsnotify from 1.5.1 to 1.5.4 (#441) | dependabot

### Documentation

- add a note about reloading the configuration when running within docker (#448) | [@leviwilson](https://github.com/leviwilson)
- README: remove incorrect mention of sending SIGUSR1 to trigger a configuration reload (#447) | [@jharley](https://github.com/jharley)

## 1.14.0 2022-05-03

### Enhancements

- Add support for environment and dataset rules with same names (#438) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

### Maintenance

- Update otlp to v0.11.0 (#437) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Update go to 1.18 (#430) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

**Note**: The docker image used to create the binaries has been updated to a version that does not suffer a [OpenSSL CVE](https://mta.openssl.org/pipermail/openssl-announce/2022-March/000219.html).

## 1.13.0 2022-04-08

### Enhancements

- Add parsing for nested json fields in the rules sampler (#418) | [@ecobrien29](https://github.com/ecobrien29)

### Maintenance

- Update husky to v0.10.3 (#431) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Bump google.golang.org/grpc from 1.43.0 to 1.45.0 (#428)
- Bump github.com/klauspost/compress from 1.13.6 to 1.15.1 (#427)
- Bump github.com/stretchr/testify from 1.7.0 to 1.7.1 (#426)
- Bump github.com/prometheus/client_golang from 1.11.0 to 1.12.1 (#390)

## 1.12.1 2022-03-28

### Fixes

- fix: error log event metadata (#422) | [@vreynolds](https://github.com/vreynolds)

### Maintenance

- Create checksums when building binaries (#423) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Cache google ko deps between workflows (#424) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.12.0 2022-02-24

### Enhancements

- feat: add support for env name from auth (#410) | [@JamieDanielson](https://github.com/JamieDanielson)

### Maintenance

- update aws-client orb to latest (#409) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.11.0 2022-02-17

### Enhancements

**Note: Environment & Services Support requires v1.12.0 and higher**

Do **not** use this version with Environment & Services.

- Add Environment & Services support (#403) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

### Maintenance

- docs: add helm charts step to releasing (#400) | [@vreynolds](https://github.com/vreynolds)

## 1.10.0 2022-02-10

### Enhancements

- added username in config for redis auth (#397) | [@ecobrien29](https://github.com/ecobrien29)
- build: add ARM64 (aarch64) RPM artifact (#395) | [@jharley](https://github.com/jharley)

### Fixes

- fix: deadlock when reloading configs (#398) | [@vreynolds](https://github.com/vreynolds)
- Fixed "honeeycomb" typo in log output when reloading config (#394) | [@looneym](https://github.com/looneym)

## 1.9.0 2022-02-01

### Enhancements

- Honor env. variable to set gRPC listener address (#386) | [@seh](https://github.com/seh)
- Add retries when connecting to redis during init (#382) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

### Fixes

- Properly set meta.refinery.local_hostname field (#387) | [@jharley](https://github.com/jharley)

### Maintenance

- docs: update rules example (#378) | [@vreynolds](https://github.com/vreynolds)
- Bump github.com/gomodule/redigo from 1.8.5 to 1.8.8 (#374)
- Bump github.com/spf13/viper from 1.9.0 to 1.10.1 (#375)
- Bump google.golang.org/grpc from 1.42.0 to 1.43.0 (#372)

## 1.8.1 2022-01-06

### Maintenance

- Add re-triage workflow (#368) | [@vreynolds](https://github.com/vreynolds)
- Bump libhoney & golang (#373) | [@lizthegrey](https://github.com/lizthegrey)
- Bump github.com/honeycombio/husky from 0.5.0 to 0.6.0 (#370)
- Bump github.com/prometheus/client_golang from 0.9.4 to 1.11.0 (#357)

## 1.8.0 2021-12-08

### Enhancements

- Make MaxBatchSize configurable (#365) | [@JamieDanielson](https://github.com/JamieDanielson)

### Maintenance

- Bump husky to v0.5.0 (#366) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)
- Bump husky to v0.4.0 (#361) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.7.0 2021-11-29

### Enhancements

- Replace internal duplicated code with Husky (#341) [@MikeGoldsmith](https://github.com/MikeGoldsmith)
  - Also fixes segfaults caused by nil appearing in OTLP data as described in (#358)
- Improves histogram buckets over the default set (#355) [@bdarfler](https://github.com/bdarfler)

### Maintenance

- Update dependabot to monthly (#356) [@vreynolds](https://github.com/vreynolds)

## 1.6.1 2021-11-10

- Revert "Use alpine as base image (#343)" (#352)

## 1.6.0 2021-11-04

- Add an --interface-names flag (#342) | [@ismith](https://github.com/ismith)

### Fixes

- bump libhoney-go to v1.15.6
- empower apply-labels action to apply labels (#344)
- Bump github.com/honeycombio/libhoney-go from 1.15.4 to 1.15.5 (#327)
- Re-add missing docker login when publishing (#338)

## 1.5.2 2021-10-13

### Fixes

- Build multi-arch docker images during publish CI step (#336) [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.5.1

### Fixes

- Fix for race condition in prometheus metrics (#324) [@estheruary](https://github.com/estheruary)
- Update race condition fix to use RWLock instead of Lock (#331) [@MikeGoldsmith](https://github.com/MikeGoldsmith) & [@robbkidd](https://github.com/robbkidd)

### Maintenance

- Build docker images on all builds and publish only on tag (#328) [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.5.0

### Enhancements

- Add dynamic sampler support to rules based samplers (#317) [@puckpuck](https://github.com/puckpuck)
- Publish arm64 Docker images (#323) [@MikeGoldsmith](https://github.com/MikeGoldsmith)

### Maintenance

- Adds Stalebot (#321) [@JamieDanielson](https://github.com/JamieDanielson)
- Switch lifecycle terminology to maintained (#315) [cartermp](https://github.com/cartermp)
- Add NOTICE (#314) [cartermp](https://github.com/cartermp)
- Add issue and PR templates (#307) [@vreynolds](https://github.com/vreynolds)
- Add OSS lifecycle badge (#304) [@vreynolds](https://github.com/vreynolds)
- Add community health files (#303) [@vreynolds](https://github.com/vreynolds)
- Bump github.com/spf13/viper from 1.8.1 to 1.9.0 (#320) [dependabot[bot]]
- Bump github.com/json-iterator/go from 1.1.11 to 1.1.12 (#316) [dependabot[bot]]
- Bump github.com/klauspost/compress from 1.13.4 to 1.13.6 (#319) [dependabot[bot]]
- Bump github.com/fsnotify/fsnotify from 1.5.0 to 1.5.1 (#311) [dependabot[bot]]
- Bump google.golang.org/grpc from 1.39.1 to 1.40.0 (#305) [dependabot[bot]]
- Bump github.com/fsnotify/fsnotify from 1.4.9 to 1.5.0 (#308) [dependabot[bot]]
- Bump github.com/klauspost/compress from 1.13.3 to 1.13.4 (#306) [dependabot[bot]]

## 1.4.1

### Fixes

- Add span.kind when ingesting OTLP (#299)

### Maintenance

- Bump google.golang.org/grpc from 1.39.0 to 1.39.1 (#300)
- Bump github.com/klauspost/compress from 1.13.2 to 1.13.3 (#301)
- Bump github.com/honeycombio/libhoney-go from 1.12.4 to 1.15.4 (#295)
- Bump github.com/klauspost/compress from 1.10.3 to 1.13.2 (#297)

## 1.4.0

### Added

- Add support for OTLP over HTTP/protobuf [#279](https://github.com/honeycombio/refinery/pull/279) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

### Maintenance

- Bump github.com/sirupsen/logrus from 1.2.0 to 1.8.1 (#290)
- Bump google.golang.org/grpc from 1.37.1 to 1.39.0 (#288)
- Bump github.com/gomodule/redigo from 1.8.4 to 1.8.5 (#287)
- Bump github.com/spf13/viper from 1.7.0 to 1.8.1 (#274)
- Bump github.com/gogo/protobuf from 1.3.1 to 1.3.2 (#242)
- Bump github.com/golang/protobuf from 1.4.3 to 1.5.2 (#252)
- Bump github.com/grpc-ecosystem/grpc-gateway from 1.12.1 to 1.16.0 (#233)

## 1.3.0

### Added

- Add support to "does-not-contain" operator on RulesBasedSampler [#267](https://github.com/honeycombio/refinery/pull/267) | [@tr-fteixeira](https://github.com/tr-fteixeira)

### Fixes

- Ensure span links and events generate events and get resource attrs [#264](https://github.com/honeycombio/refinery/pull/264) | [@MikeGoldsmith](https://github.com/MikeGoldsmith)

## 1.2.1

### Fixes

- OTLP span events are now supported, they were being dropped on the floor previously (#261) | [@dstrelau](https://github.com/dstrelau)

## 1.2.0

### Added

- Add `UseTLSInsecure` config option to skip TLS verification with Redis (#254) | [@beanieboi](https://github.com/beanieboi)
- Add `AddHostMetadataToTrace` config option to add Refinery hostname information to spans (#250) | [@jharley](https://github.com/jharley)
- Additional config validation: verify that sample rate trace field key is specified, if needed (#248) | [@paulosman](https://github.com/paulosman)

### Changed

- Remove redundant peer/api suffix from response error metrics (#247) | [@vreynolds](https://github.com/vreynolds)
    - `api_response_errors_api`, `api_response_errors_peer`, `peer_response_errors_api`, `peer_response_errors_peer`
    - replaced by `api_response_errors`, `peer_response_errors`
- Fix rules sampler to emit correct metric (#236) | [@isnotajoke](https://github.com/isnotajoke)
    - Previously `dynsampler_num_dropped` was emitted, now `rulessampler_num_dropped` will be emitted

### Maintenance

- Update README content (#239) | [@jjziv](https://github.com/jjziv)
- Move from garyburd Redigo to supported redigo (#249) | [@verajohne](https://github.com/verajohne)
- Bump google.golang.org/grpc from 1.32.0 to 1.37.1 (#253)
- Bump github.com/prometheus/client_golang from 0.9.3 to 0.9.4 (#240)
- Bump github.com/pkg/errors from 0.8.1 to 0.9.1 (#232)
- Bump github.com/stretchr/testify from 1.5.1 to 1.7.0 (#231)
- Bump github.com/jessevdk/go-flags from 1.4.0 to 1.5.0 (#230)
- Bump github.com/hashicorp/golang-lru from 0.5.1 to 0.5.4 (#229)

## 1.1.1

### Fixes

- Refinery startup issues in v1.1.0

## 1.1.0

### Improvements

- Add support environment variables for API keys (#221)
- Removes whitelist terminology (#222)
- Log sampler config and validation errors (#228)

### Fixes

- Pass along upstream and peer metrics configs to libhoney (#227)
- Guard against nil pointer dereference when processing OTLP span.Status (#223)
- Fix YAML config parsing (#220)

### Maintenance

- Add test for OTLP handler, including spans with no status (#225)

## 1.0.0

Initial GA release of Refinery
