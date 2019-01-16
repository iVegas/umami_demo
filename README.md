# Umami Demo Drupal site

## Reference

1. [Docker4Drupal README file](docker4drupal_readme)

1. [Drupal-project README file](drupal_project_readme)

## Setup initial steps

1. `cp .env.example .env`

1. Update content of `.env` file if needed.

1. `docker-compose up`

    Optionally add `-d` flag to run in detached mode.

1. `docker-compose exec php bash` to access into php container.

1. `composer install` to install dependencies.

1. `cd web` change working directory to the document root.

1. `drush si demo_umami --account-pass=admin -y` install site.

1. `sudo chown -R www-data:www-data sites/default/files` update access to the public files.

## Access to the site

Go to the [umami.localhost](http://umami.localhost/user/login). 
Use `admin` and `admin` as login and password values.

## Troubleshooting

If 80 port is already in use, update port section
in the `traefik` container at `docker-compose.yml` file.

[docker4drupal_readme]: https://github.com/wodby/docker4drupal/blob/5.4.0/README.md
[drupal_project_readme]: https://github.com/drupal-composer/drupal-project/blob/8.x/README.md
