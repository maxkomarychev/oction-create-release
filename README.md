# Create a release

"Oction" is a GitHub Action that implements a single call with 
[@octokit/request](https://www.npmjs.com/package/@octokit/request)
allowing easy interaction with GitHub REST APIs from your workflow.

Original documentation: https://developer.github.com/v3/repos/releases/#create-a-release

This action implements `POST` request to `/repos/{owner}/{repo}/releases`


# Quick start

```yaml
- uses: maxkomarychev/oction-create-release@v0.7.1
  id: my_step_id
  with:
    token: <token value>
    tag_name: <tag_name value>
- name: Print outputs
  run: |
    echo ${{ steps.my_step_id.outputs.id }}
    echo ${{ steps.my_step_id.outputs.number }}
    echo ${{ steps.my_step_id.outputs.url }}
    echo ${{ steps.my_step_id.outputs.html_url }}
    echo ${{ steps.my_step_id.outputs.assets_url }}
    echo ${{ steps.my_step_id.outputs.upload_url }}
```


# Inputs

| Name | Is required | Description |
|---|---|---|
|token|true|Token to authenticate the request
|owner|false|owner parameter
|repo|false|repo parameter
|tag_name|true|The name of the tag.
|target_commitish|false|Specifies the commitish value that determines where the Git tag is created from. Can be any branch or commit SHA. Unused if the Git tag already exists. Default: the repository's default branch (usually `master`).
|name|false|The name of the release.
|body|false|Text describing the contents of the tag.
|draft|false|`true` to create a draft (unpublished) release, `false` to create a published one.
|prerelease|false|`true` to identify the release as a prerelease. `false` to identify the release as a full release.

# Outputs

| Name | Description |
|---|---|
|id|`id` field of the response (if exists)|
|number|`number` field of the response (if exists)|
|url|`url` field of the response (if exists)|
|html_url|`html_url` field of the response (if exists)|
|assets_url|`assets_url` field of the response (if exists)|
|upload_url|`upload_url` field of the response (if exists)|

# Friendly octions

* [oction-create-deployment-status](https://github.com/maxkomarychev/oction-create-deployment-status)
* [oction-create-deployment](https://github.com/maxkomarychev/oction-create-deployment)
* [oction-create-issue](https://github.com/maxkomarychev/oction-create-issue)
* [oction-create-release](https://github.com/maxkomarychev/oction-create-release)
* [oction-lock-issue](https://github.com/maxkomarychev/oction-lock-issue)
* [oction-merge-pull-request](https://github.com/maxkomarychev/oction-merge-pull-request)
* [oction-unlock-issue](https://github.com/maxkomarychev/oction-unlock-issue)
