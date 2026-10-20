# Platform

GreekCore-owned release tooling for building, deploying, and operating production projects.

This company-maintained fork originates from the MIT-licensed `paris-phan/platform` at
`c0e695e4f6468bca272e8c649bbbfb1d244f8329`. The original license and history are retained.
Consumers pin a reviewed commit from `GreekCore/platform`; they do not fetch the personal
repository. Review ownership belongs to `@GreekCore/engineering`.

The coordinator accepts historical repository names in project configuration so existing
release artifacts remain eligible for recovery. Artifact hashes, source/run authorization,
and rollback checks are unchanged; this does not authorize an arbitrary release.

For consuming application repositories, pushes to `main` build and deploy staging. Production promotes the same verified artifact without rebuilding it, either by merging the promotion pull request that `promote.yml` maintains or by manual dispatch. Rollback uses a previously successful production release.

## Using it

Add a `platform.json` to your project and copy the [workflow examples](examples/workflows) into `.github/workflows/`, dropping the `.example` suffix. Replace the platform pins with a published commit SHA.

- [Configuration and application commands](docs/configuration.md)
- [Deploying, rolling back, and upgrading](docs/operations.md)
- [Shared conventions](docs/standard.md)
