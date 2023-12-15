# *Foreign Relations of the United States* - Not Yet Reviewed

[![exist-db CI](https://github.com/HistoryAtState/frus-not-yet-reviewed/actions/workflows/build.yml/badge.svg)](https://github.com/HistoryAtState/frus-not-yet-reviewed/actions/workflows/build.yml)

This repository contains unreviewed, work in progress on the FRUS digital archive, bound for https://github.com/HistoryAtState/frus in a future quarterly release. The volumes are posted here for advance access by researchers who would benefit from as complete a set of the series as possible. 

Before using this repository, please keep in mind the following caveats. These volumes have been delivered to us by our conversion vendor, but have not yet been reviewed by our staff. During the process of review, we look for errors in the text and the XML tags around them. While the textual content is likely quite accurate and the XML largely conforms to [our schema](https://github.com/HistoryAtState/frus/tree/master/schema), the following aspects of the volumes may well change:

1. Document boundaries (and document and chapter/compilation identifiers)
2. Index and intra-series cross-references
3. Tagging of tables, document openers, and other stylistic features

Once our staff begin review on a volume, it is deleted from this repository and moved into a branch of the main [FRUS repository](https://github.com/HistoryAtState/frus) for review in preparation for a quarterly release.


## Build

1. Single `xar` file: Files `articles.xconf` and `issues.xconf` will only contain the index, no triggers!

    ```shell
    ant
    ```

    1. Since Releases have been automated when building locally you might want to supply your own version number (e.g. `X.X.X`) like this:

    ```shell
    ant -Dapp.version=X.X.X
    ```

## Release

Releases for this data package are automated. Any commit to the `master` branch will trigger the release automation.

All commit message must conform to [Angular Commit Message Conventions](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) to determine semantic versioning of releases, please adhere to these conventions, like so:

| Commit message  | Release type |
|-----------------|--------------|
| `fix(pencil): stop graphite breaking when too much pressure applied` | Patch Release |
| `feat(pencil): add 'graphiteWidth' option` | ~~Minor~~ Feature Release |
| `perf(pencil): remove graphiteWidth option`<br/><br/>`BREAKING CHANGE: The graphiteWidth option has been removed.`<br/>`The default graphite width of 10mm is always used for performance reasons.` | ~~Major~~ Breaking Release |

When opening PRs commit messages are checked using commitlint.