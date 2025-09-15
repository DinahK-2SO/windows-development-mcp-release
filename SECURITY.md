# Release repo security guidance

- Only add minimal necessary secrets to this public repository.
- Use a Personal Access Token (PAT) with narrow scopes. Prefer creating a machine user with limited repo access if possible.
- Rotate and revoke PATs regularly.
- If possible, create a read-only install token limited to the private repository instead of full `repo` scope.
