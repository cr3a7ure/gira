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
  - what: Since there are no projects yet to fully display the actuall thought, we should create some.
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
