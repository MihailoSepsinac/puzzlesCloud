---
weight: 8
---
# README

## Navigation Configuration

In order to configure heading and footer navigation, please adjust the following file

```
/_config.yml
```

In order to configure left side navigation of the docs section, please adjust the following file

```
/_data/doc_sections.yml
```

## Logo

In order to change the logo please replace the following file in `.svg` format

```
/images/logo.svg
```

In order to change logo on the browser (favicon) please replace the following file (size 157x157)

```
/images/icon_logo.png
```

# Running Your Site Locally

1. Clone the git repository

        git clone <repo>

1. Cavigate to the newly cloned folder

        cd <repo>

1. Install a full [Ruby development environment](https://jekyllrb.com/docs/installation/)

1. Install Jekyll and Bundler

        gem install jekyll bundler

1. Install dependencies from Gemfile:

        bundle install

1. Build the site and make it available on a local server

        bundle exec jekyll serve

1. Browse to [http://localhost:4000](http://localhost:4000)
