# Actions

![](https://github.com/noteed/actions/workflows/deployment/badge.svg)

This is a sample [repository](https://github.com/noteed/actions) to show a
simple GitHub Actions workflow:

- it builds an HTML page using Nix,
- push it to [GitHub Pages](https://noteed.github.io/actions/),
- save the result to a Backblaze B2 bucket.

The name of the Backblaze B2 bucket is `noteed-actions` and the bucket is
private. The bucket name could be a secret.

Here is the URL for the secrets of this particular repository:
https://github.com/noteed/actions/settings/secrets

It seems the application key should have read-write access to the bucket.
