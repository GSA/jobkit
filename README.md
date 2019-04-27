# JobKit
This site is being jointly developed by the EOP, Dept. of Labor and GSA.

## Architecture
This is a [Jekyll-based](http://jekyllrb.com/) website designed to be published on the
[Federalist](https://federalist.18f.gov/) platform.

The website utilizes the [US Web Design Standards](https://standards.usa.gov/) and [uswds-template](https://github.com/18F/uswds-jekyll).

## Setup
These instructions explain how to set up a local development environment by installing all necessary tools and dependencies.

#### Install Ruby

Since this is a Jekyll-based website, you will need [Ruby](https://www.ruby-lang.org/en/). The best way to get Ruby is to install it via [rbenv](https://github.com/rbenv/rbenv). See the [rbenv installation instructions](https://github.com/rbenv/rbenv#installation) to set it up on your system.

#### Install Node.js and npm

We use [`npm`](https://www.npmjs.com/) to manage front-end dependencies. In order to get `npm`, install [Node.js](https://nodejs.org/). You do not strictly need `npm` to work on the website.


#### Building and previewing the website

First, install `bundler` if you don't already have it:

```
gem install bundler
```

Then install the project's Ruby dependencies:

```
bundle install --with=development
```

Then you can run the site locally with live reloading:

```
npm start
```

You should now be able to preview the site on your local machine at [http://localhost:4000/](http://localhost:4000/).

### Structure
JobKit is currently a single page website, but is architected to easily allow additional content and functionality features. 

* `_layouts/` - Contains any page layouts needed for the site. Currently, the only layout is `home.html`. Any additional layouts created should be located here.
* `pages` - Any site pages should be contained here. Currently, the only page is `landing.html`.
* `_data.yml` - Contains any data needed for the site. You'll find the `navigation.yml` file here. It contains the items for the sidenav bar.
* `_includes/` - Contains any page components. Items that are or may be used more than once should be included as a component and located here. For items in this folder, use the `{% include file_name.html %}` syntax to pull the content of the file in to your page. 

Current includes are:
** `head.html`
** `header.html`
** `sidenav.html`
** `styles.html`
** `components/footer--medium.html`
** `components/hero.html`

NOTE: items in the `_includes/components` folders are organized here so that they overwrite the original files used in the [uswds-template](https://github.com/18F/uswds-jekyll).

### Contributing content and code

1. Fork the repository (or clone it if you have commit access)
2. Create a feature branch
3. Make your changes in the feature branch
4. Commit the feature branch
5. Push the feature branch to GitHub (preview your changes at `https://federalist-proxy.app.cloud.gov/site/gsa/jobkit/BRANCH_NAME/`)
6. Open a pull request to merge the feature branch

### Proposing changes and reporting issues

Please submit a new [issue](https://github.com/GSA/jobkit/issues) if you need to:

* Report a website bug
* Propose a change to the website content

## Deploying

We make use of Federalist's continuous deployment system, which automatically deploys branches as soon as it detects a push to GitHub. Therefore, as soon as your pull request is accepted into the `master` branch, it goes to production.

