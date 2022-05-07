<p align="center">
  <a href="#"><img src="https://img.shields.io/github/repo-size/andry81-devops/gh-action--accum-content" valign="middle" alt="GitHub repo size in bytes" /></a>
• <a href="https://github.com/XAMPPRocky/tokei"><img src="https://tokei.rs/b1/github/andry81-devops/gh-action--accum-content?category=lines" valign="middle" alt="lines of text by tokei.rs" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-stats/gh-action--accum-content--gh-stats/commits/master/traffic/views">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20views|all&query=count&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/views/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub views|any|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=count&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/views/latest.json?raw=True" valign="middle" alt="GitHub views|any|14d" /></a>
• <a href="https://github.com/andry81-stats/gh-action--accum-content--gh-stats/commits/master/traffic/views">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20views|unq&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/views/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub views|unique per day|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/views/latest.json?raw=True" valign="middle" alt="GitHub views|unique per day|14d" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-stats/gh-action--accum-content--gh-stats/commits/master/traffic/clones">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20clones|all&query=count&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/clones/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub clones|any|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=count&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/clones/latest.json?raw=True" valign="middle" alt="GitHub clones|any|14d" /></a>
• <a href="https://github.com/andry81-stats/gh-action--accum-content--gh-stats/commits/master/traffic/clones">
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=Github%20clones|unq&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/clones/latest-accum.json?raw=True&logo=github" valign="middle" alt="GitHub clones|unique per day|total" />
    <img src="https://img.shields.io/badge/dynamic/json?color=success&label=14d&query=uniques&url=https://github.com/andry81-stats/gh-action--accum-content--gh-stats/raw/master/traffic/clones/latest.json?raw=True" valign="middle" alt="GitHub clones|unique per day|14d" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81-devops/gh-action--accum-content/commits">
    <img src="https://img.shields.io/github/commits-since/andry81-devops/gh-action--accum-content/latest?sort=semver&label=Github%20commits%20since%20latest" valign="middle" alt="GitHub commits since latest version" /></a>
  <a href="https://github.com/andry81-devops/gh-action--accum-content/releases">
    <img src="https://img.shields.io/github/v/release/andry81-devops/gh-action--accum-content?include_prereleases&label=latest" valign="middle" alt="latest release name" /></a>
</p>

<p align="center">
  <a href="https://github.com/andry81/donate"><img src="https://github.com/andry81/andry81/raw/master/badges/donate.svg" valign="middle" alt="donate" /></a>
</p>

---

<p align="center">
  <a href="https://github.com/andry81-devops/gh-action--accum-content/blob/master/userlog.md">Userlog</a>
• <a href="https://github.com/andry81-devops/gh-action--accum-content/blob/master/changelog.txt">Changelog</a>
• <a href="#dependecies">Dependencies</a>
• <a href="#known-issues">Known issues</a>
• <a href="#copyright-and-license"><img src="https://github.com/andry81/andry81/raw/master/badges/mit-license.svg" valign="middle" alt="copyright and license" />&nbsp;Copyright and License</a>
</p>

<h4 align="center">GitHub composite action to periodically download and accumulate content into repository.<br/>
<br/>
Tutorial to use with: https://github.com/andry81-devops/accum-content</h4>

##

# gh-action--accum-content@master

**Features**:

* Does store downloaded content in a repository on the GitHub, so all the resources does render from a repository file and does access a repository instead of an external resource, which:

  * Reduces traffic to an external resource and avoids an out-of-service case.

  * Does better cache on the GitHub side, when a resource can be checked on a cache expiration and so updated opposite to an external resource, where the resource has to be completely redownloaded.

* Content can be changed after download but before store in a repository. For example, for a SVG file - resized or cleanuped (not implemented).

* Downloads content under GitHub Actions pipeline IP.

* Repository to store content config file and content can be different, and you may directly point the content repository as commits list:
  `https://github.com/{{REPO_OWNER}}/{{REPO}}--gh-content-cache/commits/master`

* Workflow is used [accum-content.sh](https://github.com/andry81-devops/gh-workflow/blob/master/bash/cache/accum-content.sh) bash script to accumulate content

* The script does accumulate content into a repository and does update the content index file:
  `content-index.yml`

* The script can skip warnings and errors (`CONTINUE_ON_INVALID_INPUT=1`, `CONTINUE_ON_EMPTY_CHANGES=1`)

* The script can generate textual changelog file with notes about changes per commit (including changes absence in case of skipped errors or skipped content update; `ENABLE_GENERATE_CHANGELOG_FILE=1`, `CHANGELOG_FILE=".../content-changelog.txt"`)

* The script can insert the time string in format `HH:MMZ` additionally after the date in each commit message (by default inserts only a date for shorter commit messages; `ENABLE_COMMIT_MESSAGE_DATE_WITH_TIME=1`)

# USAGE

> :warning: You must replace all placeholder into respective values:

* `{{REPO_OWNER}}` -> repository owner
* `{{REPO}}` -> your repository

## Examples:

<a name="accum-content-yml">`.github/workflows/accum-content.yml`</a>:

```yml
name: "content update at least every 3 hours"

on:
  schedule:
    - cron: "0 */3 * * *"
  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

jobs:
  accum-content-cache:
    runs-on: ubuntu-latest

    steps:
      - uses: {{REPO_OWNER}}/gh-action--accum-content@master
        with:
          deps_repo_owner:          {{REPO_OWNER}}
          deps_repo_branch:         master
          deps_repo_read_token:     ${{ github.token }}

          config_repo_owner:        {{REPO_OWNER}}
          config_repo:              {{REPO}}--gh-content-cache-config
          config_repo_branch:       master
          config_repo_read_token:   ${{ secrets.READ_STATS_TOKEN }}

          store_repo_owner:         {{REPO_OWNER}}
          store_repo:               {{REPO}}--gh-content-cache
          store_repo_branch:        master
          store_repo_write_token:   ${{ secrets.READ_STATS_TOKEN }}

          store_entity_path:        owner-of-content/repo-with-content

          # config repo
          content_config_file:      repo/owner-of-content/repo-with-content/content-config.yml

          # store repo
          content_index_file:       repo/owner-of-content/repo-with-content/content-index.yml

          content_index_dir:        repo/owner-of-content/repo-with-content

          curl_flags: >-
            -H 'Cache-Control: no-cache'
            -v

          env: >-
            ENABLE_GENERATE_CHANGELOG_FILE=1
            ENABLE_COMMIT_MESSAGE_DATE_WITH_TIME=1
            CHANGELOG_FILE=repo/owner-of-content/repo-with-content/content-changelog.txt
            ENABLE_YAML_DIFF_PRINT_AFTER_EDIT=1
            CONTINUE_ON_EMPTY_CHANGES=1
            ERROR_ON_EMPTY_CHANGES_WITHOUT_ERRORS=1
          #  ENABLE_YAML_PRINT_AFTER_EDIT=1
```

> :information_source: You can use `secrets.READ_STATS_TOKEN` instead of `secrets.WRITE_STATS_TOKEN` as long as both repositories under the same repository owner.

> :warning: You must use different values for `deps_repo_owner` and `output_repo_owner` if respective repositories actually under different repository owners.

> :information_source: See <a href="https://github.com/andry81-devops/github-accum-stats#reuse">REUSE</a> section for details if you have multiple repositories and want to store all GitHub workflow scripts (`.github/workflows/*.yml`) in a single repository.

## <a name="dependecies">Dependencies</a>

* https://github.com/andry81-devops/gh-workflow

## Known Issues

https://github.com/andry81-devops/accum-content#known-issues

## Last known issues updates

https://github.com/andry81-devops/accum-content#last-known-issues-updates

## <a name="copyright-and-license">Copyright and License</a>

Code and documentation copyright 2022 Andrey Dibrov. Code released under [MIT License](https://github.com/andry81-devops/gh-action--accum-content/blob/master/license.txt)
