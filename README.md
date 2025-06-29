# reviewdog-action-code-coverage

The GitHub Action `reviewdog-action-code-coverage` is designed to seamlessly integrate with [reviewdog](https://github.com/reviewdog/reviewdog), a powerful tool that automates the code review process.
This action excels in analyzing and reporting code coverage metrics directly within pull requests or commits.
Its standout feature is the ability to automatically comment on lines of code in your pull requests that are not covered by tests.
This ensures developers are aware of which parts of their new code submissions may need additional testing, thereby preventing any decrease in the overall code coverage of the project.
This promotes rigorous testing practices and helps maintain high code quality standards.

![Image from Gyazo](https://i.gyazo.com/aa1a2b5559cf83da2b2315ef6a8d78b5.png)

## Usage

### Basic

```yml
steps:
  - uses: aki77/reviewdog-action-code-coverage@v2
    with:
      lcov_path: ./coverage/**/*.lcov
```

## Inputs

See [action.yml](action.yml)

| Name | Description | Default | Required |
| - | - | - | - |
| `fail_level` | Unless `none`, exit code 1 for reviewdog if it finds at least 1 issue with severity greater than or equal to the given level. | `none` | no |
| `filter_mode` | Filtering mode for the reviewdog command [`added`, `diff_context`, `file`, `nofilter`] | `added` | no |
| `github_token` | GITHUB_TOKEN | `${{ github.token }}` | no |
| `lcov_path` | Lcov files path. Support for glob pattern. |  | yes |
| `reporter` | Reporter of reviewdog command [github-check,github-pr-check,github-pr-review]. | `github-pr-review` | no |
| `tool_name` | Tool name to use for reviewdog reporter | `code-coverage` | no |
| `delete_previous_comments` | Delete previous comments made by the same tool | `true` | no |
