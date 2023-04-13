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
          job_name: test-job (${{ matrix.os }}, ${{ matrix.arch }})

      - name: Echo Job URL
        run: echo '${{ steps.job-url.outputs.job_url }}'
```
