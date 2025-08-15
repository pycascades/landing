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

The site is built with [lector](https://getlektor.com).
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

