# Python dockerfiles

## `Dockerfile.fat` Astropy and matplotlib with LaTeX support

This image is based on the [Python 2.7.11-wheezy](https://github.com/docker-library/python/blob/12db3f7b07f9704719657a0652357a3ae4cdc1c1/2.7/wheezy/Dockerfile)
image with the additions listed below. This should allow running most of astrophysical projects with full support for LaTeX labels in plots.
  * TeX live distribution
  * Ghostscript
  * python-pygments
  * astropy
  * matplotlib

## `Dockerfile.tweepy.dev` Development tweepy image

This image provides a throw-away python environment to play with Twitter interaction via [Tweepy](http://www.tweepy.org/).

## `Dockerfile.twit` Twit

This image provides a throw-away container posting a Twitter status update using crediantials stored outside the container.

```
docker run -i -t --rm -v /location/of/secrets:/secret mriello/twit Hello twits
```

where `/location/of/secrets` is the path to the directory containing two files: `twitter.consumer` and `twitter.access`.
The first file should have only one line containing the colon-separated consumer token and consumer secret (i.e. `token:secret`).
The second file should also have only one line and should contain the colon-separated access token and secret.

The example above will post a status update with message `Hello twits` to the account associated with the specified consumer
and access tokens and secrets.

