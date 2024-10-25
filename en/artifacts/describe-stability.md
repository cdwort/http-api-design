#### Describe stability

Currently, we describe the stability of your API at the resource-level, marking each resource and all its endpoints according to
its maturity and stability, e.g. with prototype/development/production
flags.

Our current versioning policy is that once your API is declared production-ready and stable, we do not make
backwards incompatible changes within that API version. If you need to
make backwards-incompatible changes, create a new API with an
incremented version number.

##### V3

This article describes Heroku’s commitment to compatibility for services built on the Platform API. It also describes how we will introduce changes to the API and how those changes are communicated.

Versions and resource stability
V3 is the current and only supported version of the Platform API.

Within any given version of the API, any given resource (eg. /apps, /account or /apps/:id/addons) has a specified level of stability. The stability of a resource is specified in the JSON Schema stability property. It’s also displayed in the Platform API reference document.

The stability of a resource specifies what changes (if any) Heroku will make to the resource and how changes will be communicated. The possible types of changes are detailed below. All changes are communicated in the Heroku Changelog.

There are three levels of stability: prototype, development, and production.

*Prototype*
A prototype resource is experimental and major changes are likely. In time, a prototype resource may or may not advance to production.

Compatible and emergency changes may be made with no advance notice
Disruptive changes may be made with one week notice
Deprecated resources will remain available for at least one month after deprecation

*Development*
A Development resource is a work-in-progress, but major changes should be infrequent. Development resources should advance to production stability in time.

Compatible and emergency changes may be made with no advance notice
Disruptive changes may be made with one month notice
Deprecated resources will remain available for at least six months after deprecation

*Production*
A production resources is complete and major changes will no longer occur.

*Compatible and emergency changes may be made with no advance notice*

Disruptive changes may not occur, instead a new major version is developed
Deprecated resources will remain available for at least twelve months after deprecation

*Deprecation*
Deprecated resources have a deprecated_at date property in the JSON Schema which is also displayed in the API Reference documentation. Deprecated resources will keep working for at least as long after deprecation as mandated by their stability: 1 month for prototype resources, 6 month for development resources and 12 months for production resources. Deprecated resources will not change stability.

Once a resource has been completely deactivated, it will return HTTP 410 for all requests.

Types of changes
Compatible change
Small in scope and unlikely to break or change semantics of existing methods.

Add resources, methods and attributes
Change documentation
Change undocumented behavior
Disruptive change
May have larger impact and effort will be made to provide migration paths as needed.

Change semantics of existing methods
Remove resources, methods and attributes
Emergency change
May have larger impact, but are unavoidable due to legal compliance, security vulnerabilities or violation of specification.
