# windows-development-mcp-release

This repository is a public-facing release repository for distributing the releases of
`@DinahK-2SO/windows-development-mcp` while keeping the actual code in the
private repository `DinahK-2SO/windows-development-mcp` private.

Usage

- Create a Personal Access Token (PAT) with `repo` scope (or narrower read access to the private repo) in GitHub. Keep this PAT secret.
- Add the PAT to this repository's secrets as `PRIVATE_REPO_PAT`.
- Use the Actions workflow `Release private package to Public Releases` (Workflow `release.yml`) to create a release.

Notes and security

- The PAT must have at least read access to the private repository to allow Actions to checkout the private code. Do NOT grant more permissions than necessary.
- Store the PAT in repository `Secrets` and rotate it periodically. If the PAT is compromised, revoke it immediately.

Triggering a release

- From the Actions tab in this repo, select the `Release private package to Public Releases` workflow and click "Run workflow".
- Optionally provide a tag (like `v1.2.3`). If left empty, the workflow will use the `version` field from the private repository's `package.json` and prefix it with `v`.

Validation

- After the workflow finishes, the release page will include a .tgz tarball which users can download publicly.
- Verify the tarball contents locally using `npm pack` or `tar -tzf <tarball>`.
