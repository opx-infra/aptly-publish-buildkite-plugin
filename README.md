# Aptly Publish Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) for publishing Debian packages with [Aptly](https://aptly.info).

## Example

```yaml
steps:
  - command: gbp buildpackage --git-pbuilder
    artifacts: "*.deb"
  - wait
  - plugins:
      opx-infra/aptly-publish#v0.1.0:
        download: pool/stretch/$BUILDKITE_PIPELINE_SLUG-stretch/
        distribution: stretch
```

## Configuration

### `download` (required)

The path to use for downloading artifacts to publish.

### `distribution` (optional)

The Debian distribution to publish to. The default is `stretch`.

## License

MIT (see [LICENSE](LICENSE))
