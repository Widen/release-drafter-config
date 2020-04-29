# Release Drafter Config

This is a common configuration for the [Release Drafter](https://github.com/release-drafter/release-drafter) github action.

## Public Disclaimer
```diff
- WARNING: THIS IS A PUBLIC REPOSITORY. DO NOT COMMIT ANYTHING THAT CAN NOT BE SHARED
```

## Description

[Release Drafter](https://github.com/release-drafter/release-drafter) is a Probot application that allows extending configuration from a shared repository
This allows us to standardize how our release drafts are generated and any updates will be propagated throughout without needing to
modify multiple repos

## Usage

To leverage Release Drafter and this shared config two files will need to be added to your repository.
1. `.github/workflows/release-drafter.yml` This enables the action in the repository. 
    * this can be copied directly from this shared repository
1. `.github/release-drafter.yml` this is the configuration for release-drafter to use. Contents should be 
    * If you want you can copy `.github/extension-sample.yml` -> `.github/release-drafter.yml` or the contents should be. 
    ```yaml
    _extends: release-drafter-config
    ```

## Overrides

You are able to override any config props that your team deems they'd like different from the common config.

```diff
! Although this is possible it is recommended that you stick with the common config since its a 
! safe default and will make it easy to bounce between release notes in repos.
```

```yaml
_extends: release-drafter-config
# Optionally include any values that your team would like to override
change-template: '> $TITLE (#$NUMBER)'
```