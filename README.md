# Tutorial Slides Template

This repo is the central starting point for creating slides that are derived from our tutorials, particularly those embedded in the Train the Trainer websites.

## Structure


## Publishing the Site

The Workflows section below begins to discuss this in a bit more detail, but as a practical guide to get your site/slides up-and-running.

1. Run `quarto publish gh-pages` at your command line from the root of the project
2. Respond `Yes` to the question `Publish site to X using gh-pages`
3. Let's this run for a few minutes.
4. Check on the GitHub repo that the `gh-pages` branch now exists. You can search for the text that says `X Branches`, click on this, and confirm that `gh-pages` is an option.
5. If all has been successful up to this point, confirm your site has been auto-published by going to `Settings` -> `Pages` and check for the statement `Your site is live at X`.


## Workflows

For a more detailed version of the workflows (i.e. Actions) in this repo, take a look at the [workflows README](.github/workflows/README.md).

Key pieces of information:

1. One of the workflows automatically renders the `index.qmd` file (all outputs), and hosts that as the website.
2. One of the workflows ensures consistent naming of files and folders for all html, md, qmd, css, scss, rmd, and yml files.
    - Rules: lowercase letters only, dashes between words, no numbers. Examples: `this-file/name-is-acceptable.qmd` or `folder/part-one.qmd`
3. One workflow checks that the CITATION.cff file is valid. You can ignore this one being marked as failing until you decide to publish.
4. A final workflow, `style.yaml`, runs the [R styler](https://styler.r-lib.org/reference/style_dir.html) on R-related files (including Quarto files with R chunks). **This is not run automatically because it will make a commit on the branch it runs on. Run this just before publishing.**