# meada-smoke-shared

Reusable pipelines and actions of the Meada CI smoke corpus. `meada-smoke-app` and
`meada-smoke-lib` call them; the cases and what GitHub does with each are in the app's `CASES.md`.

- `.github/workflows/`: `build.yml` (`on` as a map), `release.yml` (a list, asks to write),
  `string-on.yml` (a string), `wrapper.yml` (calls `build.yml`), `orphan.yml` (nobody calls it),
  `not-reusable.yml` (no `workflow_call`), `self.yml` (calls its own).
- Actions: the root, `setup/`, `report/` (`action.yaml`), `chain/` (calls `setup`), `image/` (a
  `Dockerfile` and no action file), `local-action/`.
- The tag `v1` is the first commit: `legacy.yml` exists there and not at the head.
