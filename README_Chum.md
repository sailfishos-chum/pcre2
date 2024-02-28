### Chum packaging for pcre2

This package is intended for building at Sailfishos Chum, and only to be
available for repositories relating to Sailfish OS Version **less than** 4.6

Previously to Sailfish OS 4.6, there was no officially shipped package for
`pcre2`, so Chum is free to provide one.

Ensuring that the package does not clash with upstream SailfishOS:

 1. The spec file has a section at the top that disables building on OBS for Chum repositories >= 4.6
 1. Up to and including git tag `10.40+git2` the spec file was a modified OpenSuSE one
 1. Starting with tag `10.42+chum1`, spec file and upstream repository follow the Sailfish OS packaging repos.
 1. Tag suffixes starting with 10.42 must not clash with the ones used by
	Jolla (usually `+gitX`. We selected the string `+chumX` for now.
