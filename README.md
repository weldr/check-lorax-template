# List runtime-install.tmpl packages

`check-lorax-template -r 34 runtime-install.tmpl`

will list the package globs from the template.

# List all installed packages

`check-lorax-template -r 34 -s /etc/yum.repos.d/fedora.repo runtime-install.tmpl`

This will depsolve the template package list using DNF and the repos specified
by the -s argument.  You can pass a repo file or repo URLs.

## Reuse temporary directory

Pass `--keep` to keep the temporary directory and on the next run pass that
path to it using `--keep --tempdir=/tmp/PATH-TO-DIR`

The directory will be named `/tmp/test-dnf.*`, or you can pass your own, but it
will be deleted if `--keep` is not passed so be careful.
