# ToS;DR Security Policy

* [Reporting a Vulnerability](./#Reporting-a-Vulnerability)
* [Security Announcements](./#Security-Announcements)
* [Acknowledgements](./#Acknowledgements)

### Reporting a Vulnerability <a href="#tos-drsecuritypolicy-reportingavulnerability" id="tos-drsecuritypolicy-reportingavulnerability"></a>

If you think you've identified a security issue in any ToS;DR Project, please\
**do not** report the issue publicly via a mailing list, IRC, a public issue on\
our issue trackers, a merge request, or any other public venue.

Instead, report a\
[Security Vulnerability via Service Desk](https://security.tosdr.org) or via email to [security@tosdr.org](mailto:security@tosdr.org). Please include as many\
details as possible, including a minimal reproducible example of the issue, and\
an idea of how exploitable/severe you think it is.

**Do not** provide a merge request to fix the issue, as there is currently no\
way to make confidential merge requests on [http://github.com](http://github.com) .

If you have patches which fix the security issue, please attach them to your security vulnerability report as\
patch files.

Security vulnerability reports are only visible to the reporter and the ToS;DR Staff.

The next steps are then:

* The report is triaged.
* Code is audited to find any potential similar problems.
* The fix is prepared for the most recent stable branch.
* The fix is submitted to the public repository.
* On the day the issue and fix are made public, an announcement is made on the\
  [public channels listed below](./#Security-Announcements).
* The fix will be deployed into production.

### Security Announcements <a href="#tos-drsecuritypolicy-securityannouncements" id="tos-drsecuritypolicy-securityannouncements"></a>

Security announcements are made publicly via the [Confluence Docs](https://tosdrconfluence.atlassian.net/wiki/label/NEWS/security).

### Acknowledgements <a href="#tos-drsecuritypolicy-acknowledgements" id="tos-drsecuritypolicy-acknowledgements"></a>

This text was partially based on the\
[github.com/containers security policy](https://github.com/containers/common/blob/master/SECURITY.md),\
[flatpak security policy](https://github.com/flatpak/flatpak/blob/master/SECURITY.md),\
[gnome security policy](https://gitlab.gnome.org/GNOME/glib/-/blob/master/SECURITY.md).
