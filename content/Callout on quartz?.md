---
title: Building this site
draft: false
tags:
  - tutorial
  - quartz
---

> [!FAQ] Why?
> i found [this](https://quartz.jzhao.xyz/features/callouts) engine unintentionally when searching for Callouts on obsidian. just in time to replace my obsolete jekyll pages on github.

the author already have a really good tutorial.  From Initialization to hosting. 
to host on Github, [follow the instruction here](https://quartz.jzhao.xyz/hosting#github-pages) and in my case, modify `deploy.yml` to use `ubuntu-latest` on all jobs.
```
jobs:
  build:
    runs-on: ubuntu-latest
```

to setup first home page, [follow the instruction here](https://quartz.jzhao.xyz/configuration#general-configuration). in my case, i modify `pageTitle` and `baseUrl` on `quartz.config.ts`





