# renovate-config
Opinionated shareable config preset for Renovate Dependency bot

## Description

This Renovate Bot shareable config is intended for use on NPM and Yarn based Javascript projects and has been intentionally limited in scope to manage dependencies in a sane manner for that type of project.
## Usage

Add the following to your existing Renovate Bot config file as a preset using:

```json
"extends": ["github>arrrgi/renovate-config"]
```

Other config settings you add may continue to override any of the presets defined here. Feel free to fork this repo and make your own opinionated changes to support your own projects.