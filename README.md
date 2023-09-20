# Toloka documentation

Welcome to the Toloka [docs](https://toloka.ai/en/docs/).

## About the docs

The documentation is developed using [Yandex Flavored Markdown](https://github.com/yandex-cloud/yfm-docs) (YFM). See [YFM syntax](https://github.com/yandex-cloud/yfm-transform/blob/master/DOCS.md).

## Making the Toloka docs better

To contribute to the Toloka docs you need to first read the [Yandex Contributor License Agreement](https://github.com/Toloka/docs/blob/main/CONTRIBUTING.md) (CLA) text and add to your pull request, that you agree to the terms of the CLA.

If you notice a typo or error in the documentation or want to add any section, create a pull request (PR) with edits via GitHub.

## Building the Toloka docs

Before creating a pull request, build the docs locally for checking your changes. To do this, use the [yfm-docs](https://github.com/yandex-cloud/yfm-docs) tool.

1. Install **yfm-docs**:

   `npm i @doc-tools/docs -g`

   To update the version of **yfm-docs**, use the `npm i @doc-tools/docs@latest -g` command.

2. Switch to the folder with the documentation:

   `cd ./docs`

3. Build the docs:

   `yfm -c .yfm -i ./ -o /path-to/docs-gen`, where `./` is the documentation folder with the source texts (you can also use the absolute path to it), and `/path-to/docs-gen` is a folder where you want to place the generated documentation.

4. Open the `index.html` file from either the `en` or `ru` subfolder of the output folder you specified (in our case it is `/path-to/docs-gen/en` or `/path-to/docs-gen/ru`) in your favorite browser, go to the section you contributed to, and see if everything is okay.

## Licenses

© Toloka AI AG. Licensed under the Apache License, Version 2.0. See LICENSE file for more details.
