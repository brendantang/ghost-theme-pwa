# "progressive web app" Ghost theme boilerplate

This repository provides boilerplate template for developing [Ghost](https://ghost.org) themes.  
It uses a lot of the features of "modern" ui development while sticking with Ghost's out-of-the-box Handlebars [templating system](https://ghost.org/docs/api/v3/handlebars-themes/).

> For a boilerplate without any tooling other than the mandatory `gscan`, see [wisp](https://github.com/brendantang/wisp)

I see this as a good alternative to using Ghost as a [headless CMS](https://ghost.org/docs/concepts/front-end/) and relying on a framework like React or Gatsby.
Those are good options, but forgoing Ghost's Handlebars integration means:
  - You are responsible for making sure your front-end is rebuilt every time an author makes a change from the Ghost admin panel.
    - This is easily achievable using some combination of [webhooks](https://ghost.org/docs/api/v3/webhooks/) and server-side scripting or "serverless functions."
  - However, you also become responsible for providing real-time feedback on build status.
    You need to handle the case where your build fails, or where it takes longer than your user expects, or where your user's cached version of the site conflicts with the up-to-date build.

There are other good reasons to use a statically-built front end.
But if you just want snappy page renders and convenient npm tools, that's easily achievable within the Ghost handlebars theming system, which "just works" with minimal extra effort.

## Tooling

- [x] Turbolinks for snappy rendering
- [x] Webpack for javascript bundling/minification
- [x] Postcss for CSS bundling/minification
- [ ] Prettier for formatting
- [ ] linting

# Usage

`yarn build` zips the theme into dist/wisp.zip, then you can upload the theme from Ghost admin

# Developing

If you don't already have a local instance of Ghost running, set one up according to the [Ghost docs](https://ghost.org/docs/install/local/)

Use this repo as a template and clone it into `<path-to-local-ghost>/content/themes/<your-new-theme>`.

You may need to run `ghost restart` to get the admin panel to show the repo as one of the theme options you can activate.

Once the theme you're developing is active, Ghost should reflect changes you make to existing files on page reload.
You will have to run `ghost restart` whenever you rename a file or add a new one.

# references

- https://ghost.org/docs/install/local/#developing-themes
