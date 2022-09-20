[![Build Status](https://dev.azure.com/pholleran/toc-me/_apis/build/status/toc-me-CI?branchName=master)](https://dev.azure.com/pholleran/toc-me/_build/latest?definitionId=6&branchName=master)

# toc-me

tomatoes

basil

> A GitHub App built with [Probot](https://github.com/probot/probot) that runs [markdown-toc](https://github.com/jonschlinkert/markdown-toc)

## Overview

Teams often use GitHub to manage documentation. As that documentation grows navigation can become a challenge, leading to the addition of a table of contents (ToC). As the documentation is modified team members must take care to ensure the ToC links are properly nested and formatted, which can create a barrier to contribution.

This app examines each push operation for markdown files formatted to use `markdown-toc`. When such files are found, `toc-me` regenerates a new ToC for the file and inserts it in the configured location.

## Setup

### Deploy and configure the app

The [probot deployment docs](https://probot.github.io/docs/deployment/) can be followed to deploy your own version of `toc-me`. You will need to define an additional environment variable `APP_NAME` and populate it with the exact name of your GitHub App.

### Configuring markdown files for TOC

`toc-me` will run on properly configured markdown files

#### Inserting a new TOC in a markdown file

Edit your markdown file to include the following line where you would like the ToC inserted:

```
<!-- toc -->
```

#### Updating an existing TOC

`toc-me` will automatically update a ToC previously generated by the app.

### Configuration options

`toc-me` supports the optional use of a `toc.yml` configuration file in the `.github` directory of repositories in wihch the app is installed. Parameters [supported by markdown-toc](https://github.com/jonschlinkert/markdown-toc#options) can be defined in the file.

For example:

```yaml
append: 'this string will be appended to the end of the ToC'
```

## Contributing

If you have suggestions for how `toc-me` could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the [Contributing Guide](CONTRIBUTING.md).

## License

[ISC](LICENSE) © 2018 Philip Holleran <pholleran@github.com>
