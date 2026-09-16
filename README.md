# Website

A ready-to-use Drupal project template.

The site templates use the [UI Suite UIkit](https://www.drupal.org/project/ui_suite_uikit) theme,
with [UIkit](https://getuikit.com) and [HTMX](https://htmx.org), on top of Drupal and
[Display Builder](https://www.drupal.org/project/display_builder). No Layout Builder and no Drupal Canvas.

The project requires only the [Webship](https://www.drupal.org/project/webship) installer and three site
templates. The installer lists them:

- [Website Starter](https://www.drupal.org/project/website_starter): a Display Builder page layout and content
  displays made of UIkit components, menus and default content.
- [Webship Starter](https://www.drupal.org/project/webship_starter): documentation, products and releases, a
  newsletter and social sharing.
- [Webship Portal](https://www.drupal.org/project/webship_portal): the Webship.co portal, with Webtheme.

## Create a project

Composer runs inside DDEV, so nothing is needed on your machine but DDEV itself.

```shell
mkdir -p ~/workspace/projects/my-website
cd ~/workspace/projects/my-website
ddev config --project-type=drupal11 --docroot=web --php-version=8.4
ddev start
ddev composer create-project drupal/website:^1.0@alpha
```

## Install the site

Open the site and follow the installer, where you pick the site template:

```shell
ddev launch
```

Or install from the command line, with the Webship Starter site template:

```shell
ddev drush si -y webship --account-name=webmaster --site-name="My Website" installer_site_template_form.add_ons=webship_starter
```

Use `website_starter`, `webship_starter` or `webship_portal` as the site template.

## Project layout

| Path | Content |
|---|---|
| `web/` | Drupal root (core, contrib modules and themes) |
| `web/profiles/contrib/webship` | The Webship installer, uninstalled after the installation |
| `recipes/website_starter` | The Website Starter site template |
| `recipes/webship_starter` | The Webship Starter site template |
| `recipes/webship_portal` | The Webship Portal site template |
| `vendor/` | Composer dependencies, Drush |

## What is inside

- Drupal core 11.4 with the Standard recipe.
- UI Patterns 2, UI Styles, UI Icons, UI Skins.
- Display Builder: page layouts, entity view displays and views.
- UI Suite UIkit theme (UIkit 3.25).

## Maintainers

- Rajab Natshah: [RajabNatshah](https://www.drupal.org/u/rajabnatshah)
