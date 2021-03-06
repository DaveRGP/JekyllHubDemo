---
layout: post
title: Write a post
---

This post will show you how to write a markdown post for Jekyll on GitHub Pages. 

## Clone to GitHub Desktop

You _could_ use the Editor on GitHub.com, but that's a bit limited, lets do some changes locally. Click the `Clone or download` button and click Open in Desktop.

![Clone to GitHubDesktop]({{ site.github.url }}/assets/write-jekyll-post/1_clone_to_desktop.PNG)

## Open in GitHub Desktop

Load up GitHub Desktop and find your repo.

![Open in GitHub Desktop]({{ site.github.url }}/assets/write-jekyll-post/2_open_in_desktop.PNG)

## Open in Atom

Use the quick access `Atom` button in GitHub Desktop to open the repo in Atom text editor.

![Open in Atom]({{ site.github.url }}/assets/write-jekyll-post/3_open_in_atom.PNG)

## Make a new folder

Use the right click to open the `New Folder` dialogue in Atom.

![Make a new folder]({{ site.github.url }}/assets/write-jekyll-post/4_new_folder.PNG)

## Name `_posts`

Name the new folder `_posts`. __This is really important. If you don't you're going to have a bad time.__

![Name posts]({{ site.github.url }}/assets/write-jekyll-post/5_name_folder.PNG)

Behind the scenes Jekyll is looking for this folder when the repo is hosted on the website. It will use the Markdown files in this folder to build the individual blog posts.

## New file

Use the right click again to open the `New File` dialogue in Atom.

![New file]({{ site.github.url }}/assets/write-jekyll-post/6_new_file.PNG)

## Name `2017-03-26-setup-github-pages` (or something similar)

Name the new folder `2017-03-26-setup-github-pages` or something similar. __This is also really important. If you don't you're going to have a bad time.__

![Name file]({{ site.github.url }}/assets/write-jekyll-post/7_name_file.PNG)

Behind the scenes Jekyll is looking for names with this structure when the repo is hosted on the website. It will use the structure of the file names to associate the date it was published with the file. The generic structure to use is `YYYY-MM-DD-my-post-title`.

## Include YAML frontmatter

Duplicate the following identically (or at least similarly) at the start of your file. __This is also also really important. If you don't you're going to have a bad time.__

```yaml
---
layout: post
title: Write a post
---
```

Behind the scenes Jekyll is looking for this at the start of the files when the repo is hosted on the website. It will use this to associate metadata to the file. This is a minimal example, but they can be much more developed.

## Write some Markdown and Liquid objects

Markdown is a really convenient way to encode formatting into text files. It doesn't break the flow of the text file when it is being read raw, and is much easier to learn and type without errors than html.

Liquid is a templating language which is used to provide logic and variables to a page which is rendered through Jekyll.

You don't _need_ to use the nested structure here to locate image files, I just find it helps.

```markdown
## Start new repo

Before you can start a  GitHub Page site, you need a GitHub repository! A quick way to start one is by going to github, signing in, and clicking the `+` button.

![Start new repo]({{ "{{ site.github.url " }}}}/assets/setup-github-pages/1_new_repo.PNG)
```

### Markdown
In this example the `##` denotes a second level header in Markdown. You can learn more about Markdown from your README that GitHub filled out for you in the last post.

Markdown is also used to include a picture in the document via `![New repo](path/to/file.pic)`, however we've also used a Liquid object...

### Liquid
When the site is built Jekyll will replace this section `{% raw  %}{{ site.github.url }}{% endraw %}` with the actual url of your site hosted by GitHub. Remember the last part of the last post? That url that GitHub assigned you which is recorded in your repo settings.

You should get used to using Liquid, and you should always use `{% raw  %}{{ site.github.url }}{% endraw %}` when making pages to host on GitHub Pages. __This is also also also really important. If you don't you're going to have a bad time.__

## Commit your changes

Save your file and head back to GitHub Desktop. Commit your changes and then `sync` your changes back to the web hosted version.

![Commit your changes]({{ site.github.url }}/assets/write-jekyll-post/10_commit_changes.PNG)

In my example I've already made a few changes. I've also made a new branch called gh-pages to test out my changes before commiting to the main branch. You can change the branch the site is built from in the settings page of the repo, however the branch has to be called either `master` or `gh-pages`. __This is also also also also really important. If you don't you're going to have a bad time.__

## Find your post

After syncing changes, GitHub Pages will notice that you have a folder called `_posts`. It will look through the folder for `.md` files with a name following the structure `YYYY-MM-DD-my-post-title`, and will check the `YAML` at the front. If it finds all these in place it will then parse the Markdown and Liquid into HTML, and publish these to the internet.

It really will.

It just won't tell you where they are. Yet...
