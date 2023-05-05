# :gear: `setup-algolia-cli` ![](https://github.com/algolia/setup-algolia-cli/workflows/Tests/badge.svg)

## About
This action sets up the Algolia CLI, [`algolia`](https://www.algolia.com/doc/tools/cli), on GitHub's hosted Actions runners.

This action can be run on `ubuntu-latest` and `macos-latest` GitHub Actions runners, and will install and expose a specified version of the `algolia` CLI on the runner environment.

## Usage

Setup the `algolia` CLI:

```yaml
steps:
- uses: algolia/setup-algolia-cli@master
```

A specific version of the `algolia` CLI can be installed:

```yaml
steps:
  - uses: algolia/setup-algolia-cli@master
    with:
      version:
        1.2.0
```

The credentials for the `algolia` CLI can be set using the `ALGOLIA_APPLICATION_ID` and `ALGOLIA_ADMIN_API_KEY` environment variables, which can be set using [GitHub Secrets](https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets):

```yaml
steps:
  - uses: algolia/setup-algolia-cli@master
  - name: Import settings
    run: algolia settings import MY_INDEX -F deploy/settings.json
    env:
      ALGOLIA_APPLICATION_ID: ${{ secrets.ALGOLIA_APPLICATION_ID }}
      ALGOLIA_ADMIN_API_KEY: ${{ secrets.ALGOLIA_API_KEY }}
```

## Inputs
The actions supports the following inputs:

- `version`: The version of `algolia` to install, defaulting to `latest`

## Further reading
Read the [Algolia CLI documentation](https://www.algolia.com/doc/tools/cli) to learn more about the `algolia` CLI.

## License
[MIT](LICENSE).