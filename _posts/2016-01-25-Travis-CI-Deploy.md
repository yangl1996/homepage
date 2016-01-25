---
layout: minimal_project
project: True
title: Travis-CI Deploy
introduction: A minimal Python HTTP server listening to GitHub webhook and executes some script upon successful Travis-CI build.
ghlink: https://github.com/yangl1996/travis-ci-deploy
---

I wrote this script initially for my own use. Travis-CI updates GitHub repository status upon successful/failed builds, and a webhook call is sent everytime the status is changed. This server triggers a certain script, such as restarting the server process, upon successful build. Combining this and Travis-CI, we achieve Continuous Deployment.

For additional how-to and source code, please checkout [this repository](https://github.com/yangl1996/travis-ci-deploy).

Additional features in plan:

* A simple web page displaying current branch/commit/update time
* Support multiple repositories/branches
* Call GitHub Deployment API to update deploy status
* Wechat/Slack integration
