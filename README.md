# Release Drafter Config

This is a common configuration for the [Release Drafter](https://github.com/release-drafter/release-drafter) github action.

## Description

[Release Drafter](https://github.com/release-drafter/release-drafter) is a Probot application that allows extending configuration from a shared repository
This allows us to standardize how our release drafts are generated and any updates will be propagated throughout without needing to
modify multiple repos

## Usage

```yaml
_extends: Widen/release-drafter-config
```

## Overrides

You are able to override any config props that your team deems they'd like different from the common config.

**Note**: Although this is possible it is recommended that you stick with the common config since its a safe default
and will make it easy to bounce between release notes in repos.

```yaml
_extends: Widen/release-drafter-config
# Optionally include any values that your team would like to override
change-template: '> $TITLE (#$NUMBER)'
```