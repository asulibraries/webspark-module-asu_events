# ASU Libraries fork of [asu_events](https://github.com/ASUWebPlatforms/webspark-module-asu_events)

## Installation Steps
1. add VSC for github repo in composer.json
2. Add patch for entity_embed in the composer.json so that you can have more theme suggestions
    ```
    "drupal/entity_embed": {
        "Add theme suggestions -  https://www.drupal.org/project/entity_embed/issues/3136142": "https://www.drupal.org/files/issues/2020-05-13/add-theme-suggestions-3136142-6.patch"
    },
    ```
3. Composer require the module (will add dependencies) - `composer require 'asuwebplatforms/webspark-module-asu_events:dev-master'`
4. Enable the module (will enable dependencies) - `drush pm-enable asu_events`
5. Download the font awesome icon picker library in the libraries directory - `drush fa:download-iconpicker`

## For Maintaining in Github
1. Clone the github repo from here: `git clone https://github.com/asulibraries/webspark-module-asu_events`
2. Add a second upstream for the upstream github repo: `git remote add upstream https://github.com/ASUWebPlatforms/webspark-module-asu_events`
3. You can fetch upstream by doing `git fetch upstream` and merge upstream with `git merge upstream/master`
4. If there are merge conflicts, address them and commit and push back up.

## Updating after changes in Github
1. `composer update asuwebplatforms/webspark-module-asu_events` will pull the latest commits on the master branch from our fork in github.
2. if there are changes in the config direction, then do a partial config import with something like `lando drush config:import --partial --source /app/web/modules/composer/webspark-module-asu_events/config/install`