# twang817/job-url-action

Retrieves the job url given a job name.

## Example

```yaml
  test-job:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        os: ["linux", "darwin"]
        arch: ["x86", "arm64"]
    steps:
      - name: Get Job URL
        id: job-url
        uses: twang817/job-url-action@v1
        with:
          github_token: ${{ steps.generate_token.outputs.token }}
          job_name: 'test-job (${{ matrix.arch }}, ${{ matrix.os }})`

      - name: Echo Job URL
        runs: |
            echo '${{ steps.job-url.outputs.result }}'
```
