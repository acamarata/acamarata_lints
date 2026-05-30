# acamarata_lints

Shared Dart and Flutter lint rules for [acamarata](https://github.com/acamarata) packages.

Extends [`flutter_lints`](https://pub.dev/packages/flutter_lints) with additional strict rules used across all acamarata Dart and Flutter packages. One include, consistent style everywhere.

## Install

Add to your `pubspec.yaml`:

```yaml
dev_dependencies:
  acamarata_lints: ^1.0.0
```

Run:

```sh
dart pub get
```

## Usage

In your `analysis_options.yaml`:

```yaml
include: package:acamarata_lints/analysis_options.yaml
```

That is the entire setup. The package resolves the flutter_lints transitive include automatically.

To add project-specific overrides beneath the include:

```yaml
include: package:acamarata_lints/analysis_options.yaml

analyzer:
  exclude:
    - "**/*.g.dart"
    - "**/*.freezed.dart"

linter:
  rules:
    public_member_api_docs: false  # disable for app code if preferred
```

See `example/analysis_options.yaml` for a full annotated example.

## Rule Rationale

| Rule | Rationale |
|---|---|
| `prefer_single_quotes` | Consistent string quoting across all files. Matches JS convention. |
| `always_declare_return_types` | Inference alone does not communicate intent on public APIs. |
| `avoid_print` | `print()` leaks into production logs. Use a real logger. |
| `require_trailing_commas` | Trailing commas produce cleaner diffs and reduce merge conflicts. |
| `prefer_const_constructors` | Const constructors reduce Flutter widget rebuilds. |
| `avoid_dynamic_calls` | Dynamic calls bypass the type system and cause runtime errors. |
| `public_member_api_docs` | All public APIs must be documented. These are library packages. |
| `use_super_parameters` | Dart 2.17+ super-initializer syntax reduces boilerplate. |
| `avoid_positional_boolean_parameters` | Boolean positional parameters are unreadable at call sites. |
| `sort_constructors_first` | Consistent class structure across all files. |
| `curly_braces_in_flow_control_structures` | Braces prevent off-by-one bugs when adding statements to control flow. |

## Strict analyzer modes

This package enables three strict analyzer modes:

- `strict-casts`: no implicit casts between types
- `strict-inference`: type inference failures are reported
- `strict-raw-types`: raw generic types (List without a type argument) are flagged

## Requirements

- Dart SDK: `>=3.0.0 <4.0.0`
- Depends on: [`flutter_lints`](https://pub.dev/packages/flutter_lints) `>=3.0.0 <6.0.0`

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## License

MIT. See [LICENSE](LICENSE).
