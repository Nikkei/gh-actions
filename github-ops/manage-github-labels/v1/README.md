# manage-github-labels/v1

manage-github-labels/v1 synchronizes labels from a YAML/JSON file to a GitHub repository. This action works as a wrapper for [github-label-sync](https://github.com/Financial-Times/github-label-sync).

## Usage

This action refers a configuration file that defines the labels to be synchronized. The config file format is as follows [github-label-sync](https://github.com/Financial-Times/github-label-sync/tree/15a563b500b3693ddf9d5b527158ee9082e377ae#label-config-file).

## Example

```yaml
name: Example workflow to synchronize labels

on:
  push:
    paths:
      - .github/labels.yml

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: nikkei/gh-actions/github-ops/manage-github-labels/v1
```

### input

| name                 | description                                                                                                          | required | default                    |
| :------------------- | :------------------------------------------------------------------------------------------------------------------- | :------- | :------------------------- |
| `github_token`       | The Github token used to create labels to the repository                                                             | true     | -                          |
| `allow_added_labels` | Set `"true"` if you want to leave labels not defined in the yaml file. This action will delete the labels by default | false    | `"false"`                  |
| `source_path`        | Path to the config file that defines labels                                                                          | false    | `.github/labels.yml`       |
| `source_repository`  | GitHub repository to find labels definition file                                                                     | false    | `${{ github.repository }}` |
| `target_repository`  | GitHub repository where labels are synced                                                                            | false    | `${{ github.repository }}` |

### output

None
