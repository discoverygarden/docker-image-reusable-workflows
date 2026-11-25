# Reusable Docker Image Building Workflow(s)

Remember to update versions so that changes are picked up by downstream workflows.

## Smoke tests (optional)

If the calling repo contains an executable `test/smoke.sh`, `build-image.yml`
builds a local `linux/amd64` image and runs `./test/smoke.sh smoke-test:local`
before the multi-arch build and push. A non-zero exit fails the job, so nothing
is pushed (and Renovate automerge is blocked by the failing check). Repos
without the script are unaffected.
