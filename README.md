# Website

A ready-to-use Drupal project template, in the spirit of `drupal/cms`, built with
[Display Builder](https://www.drupal.org/project/display_builder) and the
[UI Suite UIkit](https://www.drupal.org/project/ui_suite_uikit) design system.

The site itself is installed by the [Website Starter](https://www.drupal.org/project/website_starter) recipe:
a Display Builder page layout and content displays made of UIkit components, menus and default content.

## Create a project

```shell
composer create-project drupal/website my_site
cd my_site
```

## Install the site

With DDEV:

```shell
ddev config --project-type=drupal --docroot=web --project-name=my-site
ddev start
ddev drush site:install recipes/website_starter -y
ddev launch
```

Without DDEV, point a web server to `web/` and run:

```shell
vendor/bin/drush site:install recipes/website_starter --db-url=mysql://user:pass@localhost/db
```

## Project layout

| Path | Content |
|---|---|
| `web/` | Drupal root (core, contrib modules and themes) |
| `recipes/website_starter` | The Website Starter recipe, applied on installation |
| `vendor/` | Composer dependencies, Drush |

## What is inside

- Drupal core 11.4 with the Standard recipe.
- UI Patterns 2, UI Styles, UI Icons, UI Skins.
- Display Builder: page layouts, entity view displays and views.
- UI Suite UIkit theme (UIkit 3.25).

## Maintainers

- Rajab Natshah: [RajabNatshah](https://www.drupal.org/u/rajabnatshah)
