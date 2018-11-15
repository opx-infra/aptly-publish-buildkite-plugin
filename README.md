# Aptly Publish Buildkite Plugin

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) for publishing Debian packages with [Aptly](https://aptly.info).

## Example

```yaml
steps:
  - command: build.sh
    artifacts: "pool/stretch-amd64/*"
  - wait
  - plugins:
      opx-infra/aptly-publish#v0.1.2:
        download: pool/stretch-amd64
        distribution: stretch
        unstable: false
```

## Configuration

### `download` (required)

The path to use for downloading artifacts to publish.

### `slug` (optional)

Append `${BUILDKITE_PIPELINE_SLUG}` to the `download` path.

### `distribution` (optional)

The Debian distribution to publish to. The default is `stretch`.

### `unstable` (optional)

Additionally publish package to unstable release.

## License

MIT (see [LICENSE](LICENSE))
