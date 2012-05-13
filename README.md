Trac - GitHub integration
=========================

This Trac plugin provides three features:

- update Trac's database after each commit on GitHub — by doing the equivalent
  of `trac-admin TRAC_ENV changeset added ...`;
- update a local clone of a GitHub repository after each commit (optional);
- replace Trac's built-in browser by GitHub's (optional).

Featurewise this is equivalent to https://github.com/davglass/github-trac but
it has no external dependencies and makes better use of APIs in Trac >= 0.12.

It was written for https://code.djangoproject.com/ and is released under the
BSD license.

Requirements
------------

If you're running Trac < 0.13, install http://trac-hacks.org/wiki/GitPlugin.

Setup
-----

[components]
trac.versioncontrol.web_ui.browser.BrowserModule = disabled
trac.versioncontrol.web_ui.changeset.ChangesetModule = disabled
tracext.git.* = enabled
tracext.github.* = enabled

[github]
autopull = enabled
repository = <user>/<project>
token = <secret token>