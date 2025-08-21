# Landing page

This is the landing page for www.pycascades.com.

## Site layout

This repo manages content shared between years:
- Code of Conduct
- blog/news
- rss for blog

Each year's homepage is hosted under www.pycascades.com/<year>,
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

The site lives on Github Pages. Deployments can be triggered from the browser
by navigating to the admin page, then clicking the icon of the cloud with
an upward arrow, or by running:

```
$ lektor deploy
```


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