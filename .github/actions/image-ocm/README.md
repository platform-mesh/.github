# Image OCM component

Build, sign and publish an OCM component from an image and its SBOMs.
Replaces `.github/workflows/job-image-ocm.yml`.

Call this composite action directly from the publishing workflow's job.
Calling it through a reusable workflow still signs as that reusable workflow.

```yaml
jobs:
  image-ocm:
    needs: [build, sbom]
    runs-on: ubuntu-24.04-arm
    permissions:
      contents: read
      packages: write
      id-token: write
    steps:
      - uses: platform-mesh/.github/.github/actions/image-ocm@<commit-sha>
        with:
          imageReference: ghcr.io/platform-mesh/my-component:${{ needs.build.outputs.version }}
          appVersion: ${{ needs.build.outputs.version }}
          repoName: my-component
          commit: ${{ github.sha }}
```

Replace the action ref, job dependencies and build outputs with your workflow's values.
The runner must be Linux, AMD64 or ARM64, with Bash and Python 3.

The action downloads the `sbom` artifact from the current run.
It must contain `sbom-cyclonedx.json` and `sbom-spdx.json`.
Use `extraResourcesArtifact` for files referenced by `extraResources`.
Check out the publishing repository first if resources need other repository files.

Registry authentication uses the calling job's GitHub token.
Signing uses GitHub OIDC, with signature name `platform-mesh` and expected identity
`https://github.com/${{ github.workflow_ref }}`.
No RSA signing secrets are needed.
