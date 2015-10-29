---
layout: minimal_project
project: True
title: CentOS Docs Toolchain
introduction: My GSoC 2015 project - Implement and create new documentation toolchain for CentOS
ghlink: https://github.com/yangl1996/docs-toolchain
---

This is my GSoC 2015 project, carried out with Kunaal Jain, mentored by Karsten Wade and helped by Pierre-Yves Chibon.

Our goal is to provide new contributors with a way to write and submit docs to CentOS easily. And for staff of CentOS, we
want to build a platform for them to review, accept and tag the docs. The toolchain should be independent from third-party
services or software.

We use GitHub as a hub to collect docs from contributors. Authors just open a pull request to submit a new article, and
the toolchain mirrors it to Pagure (an opensource git forge). Pagure acts as the paltform for staff to review and accept
docs. Communication between authors and staff is done by posting comments under either platform - GitHub or Pagure. Comments
are synced between the two platfroms, so no one need to leave its own platform, thus enhancing usability.

Kuannl and I have completed the basic toolchain in this year's GSoC, and we have a schedule to expand it. Also, we are
working to get the toolchain integrated into CentOS's infrastructure.

Another goal of the toolchain is to make docs usable among a wide range of projects - all relevant upstream projects.
A doc describing how to set project A up in CentOS will be synced to project A's docs repository. We are exploring a way
to implement this idea.
