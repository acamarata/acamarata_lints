# Changelog

All notable changes to this project are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
This project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-05-28

### Added

- Initial release: `analysis_options.yaml` extending `flutter_lints/flutter.yaml`
- Strict acamarata rule overrides:
  - `prefer_single_quotes` — consistent string quoting
  - `always_declare_return_types` — explicit return types on all functions
  - `avoid_print` — no print() in library code
  - `require_trailing_commas` — cleaner diffs and merge conflict reduction
  - `prefer_const_constructors` + const variants — reduces Flutter rebuilds
  - `avoid_dynamic_calls` — no dynamic type invocations
  - `public_member_api_docs` — all public APIs documented
  - `use_super_parameters` — Dart 2.17+ initializer syntax
  - `avoid_positional_boolean_parameters` — boolean parameters must be named
  - `sort_constructors_first` — consistent class member ordering
  - `curly_braces_in_flow_control_structures` — always use braces
- Analyzer strict mode: `strict-casts`, `strict-inference`, `strict-raw-types`
- `example/analysis_options.yaml` showing the consumer include pattern
- `lib/acamarata_lints.dart` placeholder (lint packages export nothing)
- MIT license, README with install/usage/rule rationale table

[Unreleased]: https://github.com/acamarata/acamarata_lints/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/acamarata/acamarata_lints/releases/tag/v1.0.0
