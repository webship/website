# Website — agent guide

Composer project template (`drupal/website`, type `project`) in the spirit of `drupal/cms`: Drupal core
11.4, Drush and the `drupal/website_starter` recipe (Display Builder + UI Suite UIkit). Part of the Webship
Workspace (`~/workspace/products`): DDEV only.

## Rules

- The template holds no site code: everything is required through Composer. The site is installed with
  `drush site:install recipes/website_starter`.
- `drupal/website_starter` is kept in `recipes/` (not unpacked), so the site can be (re)installed from it.
- No Layout Builder and no Canvas: the displays are built with Display Builder.

## Test

A local build uses path repositories until the packages are released on drupal.org:

```shell
cd ~/workspace/test
composer create-project drupal/website websitetpl --repository='{"type":"path","url":"../products/website"}'
```

With DDEV, run Composer inside the container with the products directory mounted.
