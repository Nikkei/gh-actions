# generate-terraform-docs

Generate terraform docs with PR

## Description
### input

| name                    | description                                        | required | default |
| :---------------------- | :------------------------------------------------- | :------- | :------ |
| `github-token`          | The Github token used to merge PR                  | true(*)  | -       |
| `disable-auto-pr-merge` | Whether or not to disable automatically merging PR | false    | `false` |

(*) true if `disable-auto-pr-merge` is false

### output

None
