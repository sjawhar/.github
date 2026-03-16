# sjawhar/.github

Shared GitHub Actions for sjawhar repos.

## Composite Actions

### `sami-version`

Computes a deterministic version tag from project metadata.

```yaml
- uses: sjawhar/.github/.github/actions/sami-version@v1
  id: version
  with:
    source: cargo          # cargo, bun, or node
    manifest_path: cli/Cargo.toml  # optional, defaults to root
```

Outputs: `version`, `tag`, `timestamp`

### `sami-release`

Creates a GitHub Release and uploads assets.

```yaml
- uses: sjawhar/.github/.github/actions/sami-release@v1
  with:
    tag: ${{ steps.version.outputs.tag }}
    files: dist/*.*
```
