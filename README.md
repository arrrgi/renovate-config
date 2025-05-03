# renovate-config

Opinionated shareable config preset for Renovate Dependency bot

## Description

This Renovate Bot shareable config is suitable for use on a variety of projects
and has been intentionally limited in scope to manage dependencies in a sane
manner. The config is designed to be opinionated but flexible enough to allow
for customisation.

## Usage

Add the following to your existing Renovate Bot config file as a preset using:

```json
"extends": ["github>arrrgi/renovate-config"]
```

Other config settings you add may continue to override any of the presets
defined here. Feel free to fork this repo and make your own opinionated changes
to support your own projects.

## Customization

Additional customizations can be included from this repo simply by adding them
as extensions to the standard Renovate config. For example:

```json
"extends": [
  "github>arrrgi/renovate-config",
  "github>arrrgi/renovate-config:regexManager"
]
```

### Additional Presets

#### Regex Manager - `github>arrrgi/renovate-config:regexManager`

This preset is used to manage regex-based dependencies in YAML files. Package
names and versions are extracted from the source files and updated accordingly.
It provides a flexible way to handle versioning and dependency updates in a
consistent manner.

YAML files should be formatted as follows:

```yaml
versions:
  age: "1.21.0" # renovate: depName=Filosottile/age dataSource=github-releases versioning=semver
```

The regex manager expects the following mandatory fields to be present in the
YAML file:

- **"x.y.z"** - Quote enclosed version number of the dependency.
- **depName** - The name of the dependency.

The regex manager also supports the following optional fields:

- **dataSource** - The source of the dependency (e.g., GitHub releases).
- **versioning** - The versioning scheme used for the dependency (e.g., semver,
  loose, pep440).

If neither the `dataSource` nor `versioning` fields are provided, the regex
manager will default to using `github-releases` as the data source and `semver`
as the versioning scheme.

A simplified example of a YAML file with the regex manager (without optional
fields) is as follows:

```yaml
versions:
  age: "1.21.0" # renovate: depName=Filosottile/age
```

Further information on the supported data sources, versioning schemes and the
**Regex** Custom Manager can be found here:

- [Data Sources](https://docs.renovatebot.com/modules/datasource/)
- [Versioning](https://docs.renovatebot.com/modules/versioning/)
- [Custom Managers](https://docs.renovatebot.com/modules/manager/regex/)
