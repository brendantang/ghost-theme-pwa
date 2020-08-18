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
- [x] Prettier for formatting
- [x] linting with eslint and stylelint

## Using the template

> If you just want to use the theme, you download https://github.com/brendantang/ghost-theme-pwa/raw/master/dist/pwa-theme.zip and upload it to your Ghost site from the admin panel.  
> But you probably want to use this theme as a starting point for development!

If you don't already have a local instance of Ghost running, set one up according to the [Ghost docs](https://ghost.org/docs/install/local/)

Use this repo as a template and clone it into `<path-to-local-ghost>/content/themes/<your-new-theme>`.

You will need to run `ghost restart` to get the admin panel to show the repo as one of the theme options you can activate.

Once the theme you're developing is active, Ghost should reflect changes you make to existing template files on page reload.
However, the styles and javascript require a build step.

The `dev` script will watch `src/` for changes and automatically rebuild your bundles to `assets/`, but you will still have to run `ghost restart` to see the changes reflected on your site!

Run `yarn prettier` to format in place, `yarn lint` to lint both css and javascript, and `yarn gscan` to invoke the Ghost test suite to make sure your theme is compatible with Ghost 3.

Finally, tun `yarn build` to build your assets and zip up your theme to `dist/`.
