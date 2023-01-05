# gira

A foster child of Jira and Git.
Use a familiar technology (git) and a familiar logic (jira) in your repo.

> *This is work in progress if you happen to stumble upon.
I have not tried implementing those thoughs/conventions on any project yet
for a great amount of time, neither with a team.*

## Conventions

If you ever happen to design and develop any sort of software project, you realise
what a great tool git is. Well, someone might say that you cannot build
software without git, or another repository management tool. Thus, as a
developer in one or another level you are at least familiar with git and
you will not quit using it any time soon.
> So, we are about to use already familiar tools for our job.

As long as you have developed with a team of other developers, or even
alone for a company/manager you realise that there should be something
to track the progress, break the job in smaller tasks, keep track of ideas,
document businness logic and tie it with technical details.

For many organisations a kanban board, a todo list etc is the way to do it.
Thus, jira and other tools like it, whether you like it or hate it, do a job
and a lot of people are familiar with. Its a way to organise the tasks at
hand, and people are acustomed to use such variants.
> So, we are about to use already familiar notions and procedures.

The thought process here is to use the semantics of kanban tools (jira)
with the help of git.
An one man show or a team of 3, does not need another tool and another environment
to keep track of a relatively small project and add some spicy bureaucracy
on top of it.

On the same time, the need to track in an organised way the work done and
to be done is considered vital. Especially if you jump around projects
a lot and have to switch between contexts.

## What and How

gira, is one file, lets call it `STATUS.md` and some conventions we use
between us to communicate and describe the job at hand. Currently it is
in early steps of realisation. As someone will try to use it on personal
projects and maybe with a small we might see whether it is any good or not.

> Write up a series of information inside the `STATUS.md` file and let
git manage the **who**, **when**, **what** of the actual information.

In the context of standardising the job I propose some sample questions to
help populate the description fields.

### new feature description

- description:
  - what: A fancy template should be add, since that white is a bit boring.
  - why: No practical reason.
  - how: Github pages have a [guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
  - effort: dull

### bug description

- description:
  - indication: www.gira.fun does not work.
  - cause: github panel displays an error during DNS validation. `www.gira.fun` returns `InvalidDNSError`.
  - fix: Create a CNAME alias on the DNS side.
  - effort: dull

## Examples

Without further wait below is the initial version of a `STATUS.md` and a
part of `git log -p -- STATUS.md` output

### Current STATUS.md file

```markdown
# STATUS

Track project status.

## BOARD

### Work In Progress - WIP

#### feature: Add a Jekyll template

- status: WIP
- title: Add a Jekyll template
- description:
  - what: A fancy template should be add, since that white is a bit boring.
  - why: No practical reason.
  - how: Github pages have a [guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
  - effort: dull
- comments:

#### feature: Enforce HTTPS

- status: DONE
- title: Enforce HTTPS on github pages
- description:
  - what: Enforce HTTPS for the website.
  - why: Complaince rather than security at this point.
  - how: There is a guide to follow [here](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
  - effort: dull
- comments:

## BACKLOG - BLOG

### Features

#### feature: Create examples to display

- status: BLOG
- title: Create examples to display
- description:
  - what: Since there are no projects yet to fully display the actual thought, we should create some.
  - why: People (the editor too) need to see whether this thought experiment has any value.
  - how: Create some context in this file and/or some other ones too.
    If this project is too small to display the usefulness, create another one with actual code.
  - effort: doable
- comments:

### Bugs

#### bug: fix www for the domain name

- status: BLOG
- title: www has problem
- description:
  - indication: www.gira.fun does not work.
  - cause: github panel displays an error during DNS validation. `www.gira.fun` returns `InvalidDNSError`.
  - fix: Create a CNAME alias on the DNS side.
  - effort: dull
- comments: nothing
```

### Part of git log of STATUS.md

```diff
commit d6e1407c484ba424427a182456d7a51fa6f804c1
Author: cr3a7ure
Date:   Thu Jan 5 12:16:57 2023 +0200

    docs: cleanup STATUS.md

diff --git a/STATUS.md b/STATUS.md
index f78da90..a6a4f54 100644
--- a/STATUS.md
+++ b/STATUS.md
@@ -28,17 +28,6 @@ Track project status.
   - effort: dull
 - comments:

-#### feature: Add custom URL for the site
-
-- status: DONE
-- title: Add custom URL for the site
-- description:
-  - what: Buy a custom domain name to use in github pages instead of the default one.
-  - why: A custom URL might seem nice for this project and easier to share.
-  - how: Buy the domain and follow up github's [guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).
-  - effort: dull
-- comments: nothing
-
 ## BACKLOG - BLOG

 ### Features

commit 1d2ddcb662b6e03a6e718d3e4928ef6d53ad6088
Author: cr3a7ure
Date:   Thu Jan 5 12:09:42 2023 +0200

    feat: init STATUS.md, track progress like a boss
...
```
