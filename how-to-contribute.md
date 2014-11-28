Contribution guidelines for projects under https://github.com/mjambon
=====================================================================

These are general guidelines for contributing to projects hosted under
https://github.com/mjambon. If you have any questions, concerns, or
suggestions for this document, please create a Github issue for
everyone's benefit rather than a private email.


Overcommunicate
---------------

Before you start working on a feature or a bug fix, it is a good idea
to let others know that you're doing so. It is as simple as creating a
Github issue and explain your feature request in a few sentences.

It is also a happy feeling for the authors to know who's using the
software, what features people care about, and what features are
missing. Feature requests and feedback in general are already
valuable even if you're not going to contribute code.


Pull requests
-------------

Please use Github's built-in pull request feature when you are ready to
contribute some code. It works roughly as follows:

* create a Github account if you don't have one already
* fork the root repository on Github using the "Fork" button
* make changes in your repository
* as soon as you would like your code to be reviewed,
  hit the "Pull request" button on Github. Leave a clear description
  of what you're trying to achieve and of what you're expecting from
  the permanent contributors. This starts a conversation around your
  code, ideally ending up in your code being merged into the root
  repository.

Contributors who have been added a members to the root repository on
Github are asked to not work on the master branch directly. Please create
your own branch and make a pull request when you're ready.

More details on how pull requests work are given here:
https://help.github.com/articles/using-pull-requests/

It is sometimes a good idea to create a pull request before you are
done with your changes. This gives a chance to review your plans
and correct the trajectory if needed.



Programming guidelines
----------------------

In general, try to stick to the style already used in the project, or
improve it. In the latter case, please check with the main authors that
they preapprove your grand refactoring plans.

For OCaml, the official guidelines are
[here](http://caml.inria.fr/resources/doc/guides/guidelines.en.html)
and should generally be followed.

Basic formatting rules:

* do not exceed 80 characters per line in OCaml, shell
  scripts, JavaScript, C, Makefiles, Markdown, HTML, and every language
  by default.
  Exceptions will be made for verbose languages such as Java, in which
  case a maximum width of 120 is more manageable.
* use an indentation offset of 2 spaces
* do not use tabs for indentation (unless strictly required such as in
  Makefiles)
* do not leave trailing spaces; make your editor highlight them.
  Note that some older projects still have a lot of them.
  They will be removed eventually.

In OCaml, here is how you can cut a long string literal:
```ocaml
  print_string "\
    All your base are belong \
    to us.
"
```

It's the same as:
```ocaml
  print_string "All your base are belong to us.\n"
```


Testing
-------

Please add tests for your feature or your bugfix to the test suite, if
there is one. If there isn't one yet, it would be a good idea to create
one. It should just run with `make test`.

"Trust me, it works" is not enough because it doesn't guarantee that
it will keep working in the future.


Releases
--------

We are transitioning to a simpler mechanism for making releases,
allowing any member to make a release. Older releases were
uploaded to `http://mjambon.com/releases` which wasn't convenient.

Official releases are identified by a git tag such as `v12.34.5` for
version `12.34.5`. Version identifiers shall follow the [Semantic
Versioning rules](http://semver.org/).
In order to make a release, do the following:

* make sure that people in charge of the project have agreed about making
  a release and about the version identifier
* identify the file containing the version string and update it
* commit that file on the master branch
* add the version tag on that latest commit, e.g. `git tag v12.34.5`
* push the changes using `git commit origin master --tags`
* notify the opam package maintainer that a new version is available
  and give them the URL for the `tar.gz` file produced for us by
  Github, or submit a pull request to the
  [opam repository](https://github.com/ocaml/opam-repository).
  The URL
  should be `https://github.com/mjambon/`_PROJECT_`/archive/`_TAG_`.tar.gz`


Authorship
----------

`git log` is used to identify everyone's contributions to a
project. If some code or some ideas were taken from someone else,
please explain it in the commit description.

Make sure the name and email address that you're using in your git
commits identify you within your community. We cannot change them once
your commits are merged into the master branch of the root repository.
