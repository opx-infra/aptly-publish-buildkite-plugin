# Aptly Publish Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) for publishing Debian packages with [Aptly](https://aptly.info).

## Example

```yaml
steps:
  - command: gbp buildpackage --git-pbuilder
    artifacts: "*.deb"
  - wait
  - plugins:
      opx-infra/aptly-publish#v0.1.1:
        download: pool/stretch-amd64
        slug: true
        distribution: stretch
```

## Configuration

### `download` (required)

The path to use for downloading artifacts to publish.

### `slug` (optional)

Append `${BUILDKITE_PIPELINE_SLUG}-${DIST}` to the `download` location.

### `distribution` (optional)

The Debian distribution to publish to. The default is `stretch`.

## License

MIT (see [LICENSE](LICENSE))
