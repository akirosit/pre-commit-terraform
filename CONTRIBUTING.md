# Note for contributors

## Prerequisite

This repository uses pre-commit.

You need to install it and then enable it locally from the git repository :

```sh
pre-commit install -t commit-msg -t pre-commit
```

## Release a new version

Pre-commit is used alongside with release-it and the `conventional-changelog` plugin.
To create a new release :

- commit your changes without pushing them.
- go to the [`release`](./releases/) directory.
- run `npm run release` and follow the instructions.
