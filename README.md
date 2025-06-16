# Defra AI Legacy Modernisation Playbook
This is a repository for the Defra AI Legacy Modernisation Playbook, which provides guidance on how to modernise legacy systems using AI technologies.

## Viewing the Playbook

The guide is best viewed in GitHub pages at [https://defra.github.io/defra-ai-legacy-modernisation/](https://defra.github.io/defra-ai-legacy-modernisation/).

## Updating the Playbook

This documentation is written in markdown and is built using [Jekyll](https://jekyllrb.com/).

## Updating the Playbook Locally
To update the playbook locally, you will need to ensure the following pre-requisites are met and then follow the steps to build and serve the playbook.

### Pre-requisites
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/) (version 2.7 or later) - We recommend using a version manager like [rbenv](https://github.com/rbenv/rbenv) and [ruby-build](https://github.com/rbenv/ruby-build) to install Ruby.
- [Bundler](https://bundler.io/) - Install it with `gem install bundler`.

### Building the Playbook
To build and update the playbook, follow these steps:

Clone the repository:
```bash
git clone https://github.com/DEFRA/defra-ai-legacy-modernisation
```

Navigate to the repository directory:
```bash
cd defra-ai-legacy-modernisation
```

Install the required gems:
```bash
bundle install
```

Build the site:
```bash
bundle exec jekyll build --config ./defra-ai-legacy-modernisation/_config.yml
```

Serve the site locally to preview changes:
```bash
bundle exec jekyll serve --config ./defra-ai-legacy-modernisation/_config.yml
```

Open your web browser and navigate to `http://localhost:4000/defra-ai-legacy-modernisation/playbook` to view the playbook.

## Licence

THIS INFORMATION IS LICENSED UNDER THE CONDITIONS OF THE OPEN GOVERNMENT LICENCE found at:

<http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3>

The following attribution statement MUST be cited in your products and applications when using this information.

> Contains public sector information licensed under the Open Government license v3

### About the licence

The Open Government Licence (OGL) was developed by the Controller of Her Majesty's Stationery Office (HMSO) to enable information providers in the public sector to license the use and re-use of their information under a common open licence.

It is designed to encourage use and re-use of information freely and flexibly, with only a few conditions.
