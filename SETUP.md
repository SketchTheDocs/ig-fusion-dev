# Setup Guide

I took these steps to setup [reveal.js](https://revealjs.com/), create my slides, build and test presentation locally, and host it on GitHub Pages.

---

## [Reveal.js](https://revealjs.com/)

is an open-source HTML presentation framework that lets you create rich, interactive slides using open web technologies. It also powers the [Slides.com](https://slides.com/) service which features [presentations](https://slides.com/explore) that showcase the capabilities of this framework.

---

## [GitHub Pages](https://pages.github.com/)

helps you host your website directly from the GitHub repository, and even set up relevant [GitHub Actions](https://github.com/features/actions) to automate the develop-deploy cycle.

---

## Workflow

Reveal.js has support for [Markdown](https://revealjs.com/markdown/), [PDF export](https://revealjs.com/pdf-export/), [speaker notes](https://revealjs.com/speaker-view/), [code highlighting](https://revealjs.com/code/), [animatons](https://revealjs.com/auto-animate/) - and can be customized with plugins, themes etc. that I might explore later. 

For now, this is a basic workflow to get a simple deck built and hosted, then populated with content (in this case, mostly images)

<br/>

> 1. INSTALL


I went with the [basic setup](https://revealjs.com/installation/#basic-setup)

 * Create a Github repo, clone it locally.
 * Download the [reveal.js zipfile](https://github.com/hakimel/reveal.js/archive/master.zip) to that directory.
 * Take these steps to unzip & rename distribution

```
$ cd <cloned-repo>
$ cp ~/Downloads/reveal.js-master.zip  .
$ unzip reveal.js-master.zip 
$ mv reveal.js-master docs
```

Why rename it to `docs`? Because it is one of the default folder names that GitHub accepts as a [publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#publishing-sources-for-github-pages-sites) for GitHub Pages sites. My cloned repo (local) now looks like this.

```
$ ls 
LICENSE  README.md  SETUP.md  docs
```
<br/>

> 2. TEST LOCALLY

The docs/ folder will contain a starter presentation anchored at `index.html`. Start a lightweight webserver on your development device (e.g., use default _python_ server as below) from the `docs/` folder, then open up your browser to that location.

```
$ cd docs
$ python -m http.server 
Serving HTTP on :: port 8000 (http://[::]:8000/) ...
```

You should see a basic 2-slide presentation - the default scaffolded deck. The distribution also comes with a `demo.html` file which is the source for the demo seen on the [reveal.js website](https://revealjs.com/) 

Open `http://localhost:8000/demo.html` to view that presentation in your local server. This gives you a great sample to use as your starting point, or something to learn from in terms of configurations and features.


Now let's make sure the default quickstart sldies work with GitHub Pages

<br/>

> 3. PUBLISH DEFAULT SLIDES

 * Push repo changes up to GitHub. 
 * Visit the [Pages](https://github.com/SketchTheDocs/ig-fusion-dev/settings/pages) section of your repo settings.
 * Select the `docs/` folder of main branch as source
 * You'll see a notification like this:

` Your site is ready to be published at https://sketchthedocs.github.io/ig-fusion-dev/`

Visit that link - you should see the same site you saw in local testing. Your base workflow is validated!

Now, making content changes and pushing them to your repo will automatically cause hosted slides to be updated.

<br/>

> 4. AUTOMATE WITH GITHUB ACTIONS

**ToDo** I need to explore available GH actions for reveal.js. Some references of interest:
 * [Automate PDF Generation](https://4comprehension.com/github-actions-reveal-js-and-automating-pdf-conversion/)

<br/>

> 5. CUSTOMIZE YOUR PRESENTATION

Explore the [documentation](https://revealjs.com/installation/) for more. 

 * Make changes to `index.html` file for your content
 * Explore `demo.html` to get examples

My initial goal is to make a "visuals" slide deck (with one image per slide) that has built-in speaker notes and can be made to run automatically (carousel mode). Features I plan to explore:
 * [Slide Numbers](https://revealjs.com/slide-numbers/)
 * [Touch Navigation](https://revealjs.com/touch-navigation/)
 * [Speaker View](https://revealjs.com/speaker-view/)
 * [Auto-Slide](https://revealjs.com/auto-slide/)
 * [Media](https://revealjs.com/media/) - specifically with lazy-loading
 * [Video Backgrounds](https://revealjs.com/backgrounds/)
 * [Markdown](https://revealjs.com/markdown/)

Happy Talk Trails!