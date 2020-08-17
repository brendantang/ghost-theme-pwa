boilerplate for a ghost theme

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
- https://ghost.org/docs/api/v3/handlebars-themes/
