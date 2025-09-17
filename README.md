# windows-development-mcp-release

This repository is a public-facing release repository for distributing the releases of
`@DinahK-2SO/windows-development-mcp` while keeping the actual code in the
private repository `DinahK-2SO/windows-development-mcp` private.

Triggering a release

- From the Actions tab in this repo, select the `Release private package to Public Releases` workflow and click "Run workflow".
- Optionally provide a tag (like `v1.2.3`). If left empty, the workflow will use the `version` field from the private repository's `package.json` and prefix it with `v`.

Validation

- After the workflow finishes, the release page will include a .tgz tarball which users can download publicly.
- Verify the tarball contents locally using `npm pack` or `tar -tzf <tarball>`.
