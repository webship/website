# Website

A ready-to-use Drupal project template.

The site templates use the [UI Suite UIkit](https://www.drupal.org/project/ui_suite_uikit) theme,
with [UIkit](https://getuikit.com) and [HTMX](https://htmx.org), on top of Drupal and
[Display Builder](https://www.drupal.org/project/display_builder). No Layout Builder and no Drupal Canvas.

The project requires only the [Webship](https://www.drupal.org/project/webship) installer and six site
templates. The installer lists them:

- [Website Starter](https://www.drupal.org/project/website_starter): a Display Builder page layout and content
  displays made of UIkit components, menus and default content.
- [Webship Starter](https://www.drupal.org/project/webship_starter): documentation, products and releases, a
  newsletter and social sharing.
- [Webship Portal](https://www.drupal.org/project/webship_portal): the Webship.co portal, with Webtheme.
- [Drupal Website API Starter](https://www.drupal.org/project/webapi_starter): a documented JSON:API from
  `/api`, with OAuth 2.0 and Swagger UI.
- [Webships API Starter](https://www.drupal.org/project/webships_starter): a web apps gallery with
  organizations, served through the same documented API.
- [Cucumber Starter](https://www.drupal.org/project/cucumber_starter): acceptance testing management, with
  features and their Gherkin scripts, components, products and projects.

## Create a project

Composer runs inside DDEV, so nothing is needed on your machine but DDEV itself.

```shell
mkdir -p ~/workspace/projects/my-website
cd ~/workspace/projects/my-website
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/website:~1.0
```

## Install the site

Open the site and follow the installer, where you pick the site template:

```shell
ddev launch
```

Or install from the command line, with the Webship Starter site template:

```shell
ddev drush site:install ../recipes/webship_starter -y --account-name=webmaster --site-name="My Website"
```

The path is relative to the Drupal root. Use `website_starter`, `webship_starter`, `webship_portal`,
`webapi_starter` or `webships_starter`.

## Drupal 12 (beta)

The template installs the latest Drupal 11 by default. It also allows Drupal 12,
which needs PHP 8.5. To try it, set `php_version: "8.5"` in `.ddev/config.yaml`
(a DDEV release with PHP 8.5 is needed), then:

```shell
ddev restart
ddev composer require drupal/core-recommended:^12 drupal/search:^1 -W
```

Contributed modules that don't declare Drupal 12 support yet are allowed by the
`mglaman/composer-drupal-lenient` plugin (`extra.drupal-lenient.allowed-list`),
and `webship/patches` adds `^12` to their info files. Search left Drupal core in
Drupal 12; Webship Portal uses it. Some modules still fail on Drupal 12.

## Project layout

| Path | Content |
|---|---|
| `web/` | Drupal root (core, contrib modules and themes) |
| `web/profiles/contrib/webship` | The Webship installer, uninstalled after the installation |
| `recipes/website_starter` | The Website Starter site template |
| `recipes/webship_starter` | The Webship Starter site template |
| `recipes/webship_portal` | The Webship Portal site template |
| `recipes/webapi_starter` | The Drupal Website API Starter site template |
| `recipes/webships_starter` | The Webships API Starter site template |
| `recipes/cucumber_starter` | The Cucumber Starter site template |
| `vendor/` | Composer dependencies, Drush |

## What is inside

- Drupal core 11.4 with the Standard recipe.
- UI Patterns 2, UI Styles, UI Icons, UI Skins.
- Display Builder: page layouts, entity view displays and views.
- UI Suite UIkit theme (UIkit 3.25).

## Maintainers

- Rajab Natshah: [RajabNatshah](https://www.drupal.org/u/rajabnatshah)
