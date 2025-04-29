# The Open Science Community Torino Handbook

[![All Contributors](https://img.shields.io/github/all-contributors/OSCTorino/handbook?color=ee8449&style=flat-square)](#contributors)

*Questo README e' disponibile in italiano [qui](https://github.com/OSCTorino/handbook/tree/main/docs/README-it.md)*

Welcome to the repository for the OSCT Handbook.
This handbook tries to collect useful guides about Open Science and data management, and can be used and contributed to by anyone in the community.

**If you are here to read the handbook, head to [handbook.osc.to](https://handbook.osc.to/)!**

If you are here to contribute, read on!

## Contributing

The handbook is created with [hugo](https://gohugo.io/) from files here.
To contribute, first read the [guide on how to contribute to Github repositories in the handbook].

The book is re-built at every commit automatically via [Github Actions](https://github.com/features/actions): as soon as your changes are merged in the `main` branch, they will momentarily appear in the live website.

You can find all pages of the book as [markdown](https://www.markdownguide.org/) documents in the `handbook/content` directory, divided in English (`en`) and Italian (`it`) pages.

### Languages
A single page, like `some_page.md` can have a version in both languages: simply create two files in both the `it` and `en` folders with the same name.
So, for instance, this will create the same `some_page.md` entry in two different languages:
```
handbook/
    it/
        some_page.md
    en/
        some_page.md
```

The user will then be able to switch between the languages using a button at the bottom-left of the page.

If a page is only available in one language, it will come up in that same language in both the Italian and English versions of the website.
Only a page that is available in both languages will *actually* switch between the two.

### Theme
The book uses the [Hextra](https://imfing.github.io/hextra/) theme, which is oriented to guides and documentation.
Do read the documentation of the theme, and especially the section about [Hextra Shortcodes](https://imfing.github.io/hextra/docs/guide/shortcodes/).
If you don't know what shortcodes are, read [Hugo's guide to shortcodes](https://gohugo.io/content-management/shortcodes/).
The same page details Hugo's built-in shortcodes.

### Page metadata
Each page has embedded metadata, called the *front-matter*.
This metadata describes the page's title, date of creation, etc...
You can read more about this metadata [here](https://gohugo.io/content-management/front-matter/).
You define metadata as a [YAML](https://yaml.org/) block at the top of the page.
Note that the front matter **must** be at the top of the page, and enclosed in two lines with just three ticks: `---`

For example:
```yaml
---
date: 2024-01-01
draft: false
params:
  author: James Bond
title: An example page
weigth: 10
---
```
The `date` entry is the date the page is published.
`draft` may be `true` or `false` and marks if the page should be published (`false`, it's not a draft) or not (`true`, it *is* a draft).
This is useful if you want to work and collaborate on a page without showing it to the end-user.
The `title` field has the name of the page. This name will show up around the site.

All other parameters (and more!) can be seen in the [Hugo manual](https://gohugo.io/content-management/front-matter/).

### Start contributing
Ready to start contributing? Create a new page or edit one today!

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://mrhedmad.github.io/blog/"><img src="https://avatars.githubusercontent.com/u/46203625?v=4?s=100" width="100px;" alt="Luca "Hedmad" Visentin"/><br /><sub><b>Luca "Hedmad" Visentin</b></sub></a><br /><a href="#code-MrHedmad" title="Code">💻</a> <a href="#content-MrHedmad" title="Content">🖋</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->
