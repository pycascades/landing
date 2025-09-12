# Landing page

This is the landing page for www.pycascades.com.

## Site layout

This repo manages content shared between years:
- Code of Conduct
- blog/news
- rss for blog

### future state
We think we want to host each year's homepage is under www.pycascades.com/<year>,
for example www.pycascades.com/2026.


## Development

The site is built with [lektor](https://getlektor.com).
For local development, install Lektor, for instance with `uv` or `pipx`, then run:

```
$ lektor serve
```

Lektor will build the site and serve it at localhost:5000.
Most local changes trigger an automatic rebuild, but do not trigger your browser
to reload.
You can edit file contents locally, or by clicking the pencil icon in your browser
to reach the admin page.

## Deployment

The site lives on Github Pages and is deployed from `main` via Github Actions.
Any new commit to the `main` branch (e.g, a push or pr merge) automatically deploys.
If you need to redeploy, for instance if we start dynamically pulling from external 
sources in the future, you can also manually deploy via the Github Actions web UI.


## Anchors in pages

Articles using the `page` model can include the `anchors` attribute
to have a menu bar created with links to each anchor.

The `anchors` attribute should be a list of `id|Human-readable text`, then your
headings should be defined like below, anchor `my-html-id|Sweet Heading Text`
```htm
<div class="heading-wrapper">
<h3 id="my-html-id">Sweet Heading Text</h3>
<a href="#my-html-id" class="anchor-link">
  <span aria-hidden="true" class="fa-solid fa-link anchor-icon"></span>
  <span class="hidden">Section titled Sweet Heading Text</span>
  </a>
</div>
```

## testing accessibility with Axe

We're using [axe-core](https://www.deque.com/axe/) to do basic usability testing.
Thanks to PyBay for inspiration on this.
The way it works is:
1. we make a temporary directory (once per pytest invocation)
1. we make Lektor build into the temportary directory
1. we start up a web server
1. we point playwright + axe at our webserver
1. we assert that there are zero warnings

### So our site is accessible, right?

This kind of testing is the bare minimum, and we should look for ways to improve, 
especially if we can engage accessibility specialists and folks who primarily 
browse the web with screen readers

### running locally
The `uv` way:
1. uvx --with-requirements tests/requirements.txt playwright install  # this only needs to be done once
1. uvx --with-requirements tests/requirements.txt pytest
