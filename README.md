# Actions

![](https://github.com/noteed/actions/workflows/deployment/badge.svg)

This is a sample [repository](https://github.com/noteed/actions) to show a
simple GitHub Actions [workflow](https://github.com/noteed/actions/blob/main/.github/workflows/deployment.yml):

- it builds an HTML page using Nix,
- push it to [GitHub Pages](https://noteed.github.io/actions/),
- cache the result to a Backblaze B2 bucket (using `nix copy`),
- save the result to a Backblaze B2 bucket (using `b2 sync`).

The name of the Backblaze B2 bucket is `noteed-actions` and the bucket is
private. The bucket name could be a secret.

Here is the URL for the secrets of this particular repository:
https://github.com/noteed/actions/settings/secrets

It seems the application key should have read-write access (write access is not
enough) to the bucket (for the `save` step above, maybe also for the `cache`
step).

Saving to Backblaze B2 can be done with this [GitHub
Action](https://github.com/noteed/backblaze-b2-action) but since it runs in a
container, it's hard to give it the `./result` symlink to upload. Using the
`b2` command directly is easier.
