# Website — agent guide

Composer project template (`drupal/website`, type `project`) in the spirit of `drupal/cms`: Drupal core
11.4, the `drupal/webship` installer profile and three site template recipes (Display Builder + UI Suite
UIkit). Part of the Webship Workspace (`~/workspace/products`): DDEV only.

## Rules

- `require` holds only the Drupal project scaffolding, `drupal/webship` and the site templates
  `drupal/website_starter`, `drupal/webship_starter` and `drupal/webship_portal`. No other packages: each
  site template brings its own dependencies.
- The site is installed with the `webship` profile, which lists the site templates and is uninstalled
  when the installation is done.
- The site templates are kept in `recipes/` (not unpacked), so the installer finds them without Composer.
- No Layout Builder and no Canvas: the displays are built with Display Builder.

## Test

Build a throwaway DDEV sandbox from the local branch through a path repository:

```shell
ddev composer create-project --stability=dev \
  --repository='{"type":"path","url":"/var/www/html/.ddev/website"}' drupal/website:dev-1.0.x
ddev drush site:install webship -y
```
