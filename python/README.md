# Python dockerfiles

## `Dockerfile.fat` Astropy and matplotlib with LaTeX support

This image is based on the [Python 2.7.11-wheezy](https://github.com/docker-library/python/blob/12db3f7b07f9704719657a0652357a3ae4cdc1c1/2.7/wheezy/Dockerfile) image with the additions listed below. This should allow running most of astrophysical projects with full support for LaTeX labels in plots.
  * TeX live distribution
  * Ghostscript
  * python-pygments
  * astropy
  * matplotlib
