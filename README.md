# gira

A love child of Jira and Git.
Use a familiar technology (git) and a familiar logic (jira) in your repo.

> *This is work in progress if you happen to stumble upon it.
I have not tried implementing those thoughts/conventions on any project yet
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
document business logic and tie it with technical details.

For many organisations a kanban board, a todo list etc is the way to do it.
Thus, jira and other tools like it, whether you like it or hate it, do a job
that a lot of people are familiar with. It's a way to organise the tasks at
hand, and people are accustomed to use such variants.
> So, we are about to use already familiar notions and procedures.

The thought process here is to use the semantics of kanban tools (jira)
with the help of git.
An one man show or a team of 3, does not need another tool and another environment
to keep track of a relatively small project and add some spicy bureaucracy
on top of it.

At the same time, the need to track in an organised way the work done and
to be done is considered vital. Especially if you jump around projects
a lot and have to switch between contexts.

## What and How

gira, is one file, lets call it `STATUS.md` and some conventions we use
between us to communicate and describe the job at hand. Currently it is
in early steps of realisation. As someone will try to use it on personal
projects and maybe with a small team, we might see whether it is any good or not.

> Write up a series of information inside the `STATUS.md` file and let
git manage the **who**, **when**, **what** in a tracable way.

In the context of standardising the job I propose some sample questions/fields to
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
- type: feature
- description:
  - what: A fancy template should be add, since that white is a bit boring.
  - why: No practical reason.
  - how: Github pages have a [guide](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)
  - effort: dull
- comments:

#### feature: Enforce HTTPS

- status: DONE
- title: Enforce HTTPS on github pages
- type: feature
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
- type: feature
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
- type: bug
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

## Other Approaches

There are other ways to track and organise such work but I thought they
miss something in one way or add too much in another way.

### Simple TODO lists

While simple TODO lists are great to describe an idea, task or chore you
have to do inside a repository, they are too plain if you happen to jump
around repos often. One line might not be suitable to describe a task
in order for someone ( collaborator or the editor himself ) to remember the
task, its details, considerations etc.

Propose: Add an alias to `.gitconfig` displaying a simple TODO list from
the detailed file, or even a hook to extract it as separate `TODO.md`.

### conventional commits

Well, [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/)
are a way to standardise the commit message,
not the task that would be turned to commit. Conventional commits are a great
way to track **DONE** issues.

Propose:

- Embrace conventions of conventional commits on naming things,
such as the tasks need to be done ( feature/chore/fix ).
- Populate the commit message of a **DONE** task with its description.

The use of conventional commits is proposed too. Maybe add some automations,
such as create a branch directly from the `STATUS.md` file.

### External tools

[Jira](https://www.atlassian.com/software/jira), [trello](https://trello.com/), [github projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) are tools to manage such tasks, but they
might seem overkill for small projects. Keep in mind that we are investigating
a way to track per repository the tasks need to be done. Think of the overhead
to create a board/issues etc, instead of sharing a simple document and jump
right in to forming your ideas.

#### git* issues

I kept a separate paragraph for [github](https://docs.github.com/en/issues)
or [gitlab](https://docs.gitlab.com/ee/user/project/issues/) issues,
since they are the default way open source projects track their work at hand.
It seems a great choice for many collaborators and users of the final artifact.

That would be considered the next step, if the repository grows out and becomes
a thing of its self but keep the "management" at the developers team.

Propose: Possible integration between **issue** number with the tasks
described in the `STATUS.md`.

## Tooling

As described previously, git is our tool. We can leverage it and create
some useful functionality in order to ease our life.

### git aliases

If you are not familiar with git [aliases](https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases),
it's just a custom way to map specific git commands to your own wording.
For example we can say `git status` as `git s`.

On our scenarios, we could use some aliases as seen below:

```bash
# [.gitconfig]
[alias]
  # gira aliases
  #giblog = "!f() { echo \"-> BACKLOG\"; grep \"status: BLOG\" STATUS.md -A 1 --no-group-separator | grep -v status; }; f"
  giblog = "!f() { echo \"-> BACKLOG\"; grep \"status: BLOG\" STATUS.md -A 2 --no-group-separator | grep -v status | tac | sed 's/- type: /  - /g' | sed 'H;1h;$!d;g;s/\\n- title *//g'; }; f"
  giwip = "!f() { echo \"-> WORK IN PROGRESS\"; grep \"status: WIP\" STATUS.md -A 2 --no-group-separator | grep -v status | tac | sed 's/- type: /  - /g' | sed 'H;1h;$!d;g;s/\\n- title *//g'; }; f"
  gidone = "!f() { echo \"-> DONE\"; git log -p STATUS.md | grep \"status: DONE\" -A 2 --no-group-separator | grep -v status | tac | sed 's/- type: /  - /g' | sed 'H;1h;$!d;g;s/\\n- title *//g'; }; f"
```

There is some bash magic in there, but the thing is grep and filter.
Note also the pattern `gi*` so as to keep a naming convention and not mess
probably with other aliases.

- giblog: display **Backlog** in the form of `<type>: <title>`
- giwip: display **Work In Progress** in the form of `<type>: <title>`
- gidone: display **Done** in the form of `<type>: <title>` from the git log history of the file.

Those are some aliases came to mind, more will be added.

### git commit hooks

TOD

## Extras

### The effort field

Two words on the field `effort`. Effort is pretty difficult thing to evaluate.
There are a series of ways trying to quantify the effort required to
start and finish a task in a software project.

Here I chose not to quantify the effort, rather use an abstract quality definition.
Some possible categories could be:

- dull: a task boring and easy, it might take some time though
- doable: a straightforward task, being done again with variations.
- research: a task requiring some time to investigate. This could be a
totally new feature, an investigation on a bug that happens, etc. Mostly means
that we cannot proceed to execution right away.
- poc: proof of concept task, including aspects of research but not something
that would meet all quality criteria.

### The description field

The description field could be polupated with those fields according to the
task type, in order to set the common ground for the task.

As such, **what**, **why** and **how** should give the a description of the task,
its usefulness and a direction to its implementation. Hoping that those would
help the editor or another member of the team kickstart.

As far the `bug` task type, it is common knowledge that the smoke you see
is just the indication that something is not going well. That's why **indication**
is a different field from the **cause** of a bug. A bug should be described
with its **indication** at least.
