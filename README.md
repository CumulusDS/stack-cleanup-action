[![Create Release][release-badge]][release-url]
[![Import Labels][import-labels-badge]][import-labels-url]
[![Sync Labels][sync-labels-badge]][sync-labels-url]
[![PR AutoLabeler][autolabeler-badge]][autolabeler-url]
[![Assigner][assigner-badge]][assigner-url]

Description

### Inputs
#### `service`
Manually define the service being run against.
Determined automatically if left blank via CumulusDS/get-yaml-paths-action & the `file` input
Required: false
Default: ""

#### `file`
File to get yaml properties from if not defined with the `service` input
Required: false
Default: "serverless.yml"

#### `region`
Region to cleanup
Required: true

#### `role`
Role suffix to assume
Required property.

#### `duration_seconds`
Role assumption duration in seconds.
default: `3600`

#### `aws_access_key_id`
AWS Access Key ID.  Pass in from a secret.
Required property.

#### `aws_secret_access_key`
AWS Secret Acces Key.  Pass in from a secret.
Required property.

#### `role_skip_session_tagging`
Whether to tag role session or not
default: `true`

#### `account_id`
AWS account number.  Pass in from secrets.
Required property.


### Outputs
None

### Example usage
```yaml
      - name: Cleanup Stacks
        id: cleanup
        uses: CumulusDS/stack-cleanup-action@v0.0.1
        with:
          region: ${{ matrix.region }}
          role: "CI-User"
          region: "${{ matrix.region }}"
          account_id: ${{ secrets.ACCOUNT }}
          aws_access_key_id: ${{ secrets.KEY_ID }}
          aws_secret_access_key: ${{ secrets.ACCESS_KEY }}
```

[release-badge]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/release.yml/badge.svg
[release-url]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/release.yml
[import-labels-badge]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/labels_import.yml/badge.svg
[import-labels-url]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/labels_import.yml
[sync-labels-badge]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/labels_sync.yml/badge.svg
[sync-labels-url]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/labels_sync.yml
[autolabeler-badge]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/autolabeler.yml/badge.svg
[autolabeler-url]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/autolabeler.yml
[assigner-badge]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/assign.yml/badge.svg
[assigner-url]: https://github.com/CumulusDS/stack-cleanup-action/actions/workflows/assign.yml
