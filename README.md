# Craft demo site - Flukkytom

This repo contains all of the templates, front-end resources, and a MySQL database backup for “Happy Lager”, a Craft demo site.

You can find out more about Craft at [craftcms.com](https://craftcms.com/).

## Features

Happy Lager takes advantage of several Craft features:

#### Sections

The content in Happy Lager is managed from the following [sections](https://docs.craftcms.com/v3/sections-and-entries.html#sections):

* Four “Single” sections:
  - Homepage
  - About
  - Services Index
  - Work Index
* Two “Channel” sections:
  - News
  - Work
* Two “Structure” sections:
  - Locations
  - Services

#### Entry Types

The News section has two [entry types](https://docs.craftcms.com/v3/sections-and-entries.html#entry-types):

* **Article** – used to store news articles
* **Link** – used to store links to articles on other websites

#### Matrix Fields

This site has the following [Matrix fields](https://docs.craftcms.com/v3/matrix-fields.html):

* **Article Body** – used to store the varying content of the About page and News, Services, and Work entries.
* **Contact Methods** – used to store Locations’ various contact methods.
* **Services Body** – used to store information about the Services.
* **Testimonials** – used to store the Homepage testimonials.

#### Relations

This site has the following [relational fields](https://docs.craftcms.com/v3/relations.html#terminology):

* **Services Performed** _(Entries)_ – used to relate Work entries to the relevant Services entries.
* **Client Logos** _(Assets)_ – used to related the Homepage to the logos that should be displayed in the “Our Best Drinking Buddies” section.
* **Featured Image** _(Assets)_ – used to relate a featured image to News, Work, Services, and Locations entries.
* **Featured Thumb** _(Assets)_ – used to relate a featured thumbnail to Work entries.
* **Hero Image** _(Assets)_ – used to relate a hero image to the Homepage.
* **Service Icon** _(Assets)_ – used to relate an icon to Services entries.
* There are additional Assets fields within the “Article Body” and “Service Body” Matrix fields.

#### Assets

This site has the following [asset volumes](https://docs.craftcms.com/v3/assets.html):

* **Site Assets** – used to store all miscellaneous site imagery.
* **Company Logos** – used to store the company logos that are displayed on the Homepage.
* **Service Icons** – used to store Services’ icons.


## Installation

You can check out Happy Lager online from [demo.craftcms.com](https://demo.craftcms.com/).

If you want to install the site locally, follow these instructions:

1. Download/clone the repo on your computer:

   ```bash
   git clone https://github.com/craftcms/demo.git happylager.test
   ```

2. Run `composer install` within the clone:

   ```bash
   cd happylager.test
   composer install
   ```
   
3. Create a `.env` file at the root of the project with the following contents, and then update the `DB_USER` and `DB_PASSWORD` values to your database user’s credentials.

   ```dotenv
   ENVIRONMENT="dev"
   SECURITY_KEY="GoplVO9SzWSYLIvNuDBQP9M-LEJN5EWA"
   DB_DRIVER="mysql"
   DB_SERVER="localhost"
   DB_USER=""
   DB_PASSWORD=""
   DB_DATABASE="happylager"
   DB_TABLE_PREFIX=""
   DB_PORT="3306"
   ```

4. Ensure that the following files and directories have permissions that will allow PHP to read and write to them:

   - `.env`
   - `composer.json`
   - `composer.lock`
   - `config/license.key`
   - `storage/*`
   - `vendor/*`
   - `web/cpresources/*`

5. Create a new MySQL database called `happylager`, and import `happylager.sql` into it.

6. Create a new virtual host with the hostname `happylager.test` that points to the `happylager.test/web/` folder.

If you run into issues, check this: https://github.com/flukkytom/DonnieCraft/wiki/403-and-404-Errors-while-Installing-Craft-CMS-3

7. Edit your hosts file to resolve `happylager.test` to `127.0.0.1`, if necessary.

Now point your browser at `http://happylager.test`. You should see the Happy Lager homepage.

## Logging in

The Craft Control Panel is located at `http://happylager.test/admin`. You can log in with the following credentials:

* Username: `admin`
* Password: `password`

