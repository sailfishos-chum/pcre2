### Chum packaging for pcre2

This package is intended for building at Sailfishos Chum, and only to be
available for repositories relating to Sailfish OS Version **less than** 4.6.

Previously to Sailfish OS 4.6, there was no officially shipped package for
`pcre2`, so Chum is free to provide one.

4.6 now introduced a `pcre2` package, and Chum must not provide packages which
replace upstream ones, so we need to take care no pcre2 package is available.

Ensuring that the package does not clash with upstream SailfishOS:

 1. The spec file has a section at the top that disables building on OBS for
   Chum repositories >= 4.6
 1. Up to and including git tag `10.40+git2` the spec file was a modified
   OpenSuSE one. This ues different names for some of the subpackages (e.g.
   `libpcre2-16-0` vs `pcre2-utf16`. The old package names are Obsoleted, but
   not Provided from `10.42+chum2` onwards.
 1. Starting with tag `10.42+chum1`, spec file and upstream repository follow
    the Sailfish OS packaging repos.
 1. Tag suffixes starting with 10.42 must not clash with the ones used by Jolla
   (usually `+gitX`. We selected the string `+chumX` for now.

References:
 - https://irclogs.sailfishos.org/logs/%23sailfishos/%23sailfishos.2024-02-27.log.html
 - https://irclogs.sailfishos.org/logs/%23sailfishos/%23sailfishos.2024-02-28.log.html
 - https://github.com/sailfishos/pcre2
 - https://openrepos.net/content/ade/libpcre2
