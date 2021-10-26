title: Fixing Github Actions automerge with pull_request_target event
author: Linhai Shen
tags:
  - GithubActions
  - CI
  - PullRequest
categories:
  - github
date: 2021-10-26 09:10:00
---
Issue when running Github Acitons automerge:
```
2021-10-26T00:40:27.014Z INFO  Failed to merge PR: Resource not accessible by integration
2021-10-26T00:40:27.014Z INFO  Retrying after 5000 ms ... (1/6)
...
```
Github Acitons automerge:
```
name: automerge
on:
  pull_request:
    types:
      - labeled
...
```
Fixing:
```
name: automerge
on:
  pull_request_target:
    types:
      - labeled
...
```

Referenced from:
1. https://github.community/t/how-to-auto-merge-pr-from-fork/132552/5
2. https://docs.github.com/en/actions/learn-github-actions/events-that-trigger-workflows#pull_request_target
