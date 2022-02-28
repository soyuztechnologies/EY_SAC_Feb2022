# XSa HANA Analytics Adapter Release Notes

# Version 1.6.0
* Update to new java-container-security library which fixes deployment on new CF tenants
* Remove un-needed Display role
* Update to Java 8
* Update various other dependencies

# Version 1.5.10
* Fix JWT token expiration with named user connection pool

# Version 1.5.5
* Fix intermittent connection issue when connection left idle.
* Fix incorrect HeartBeat plugin information.
* Set application name properly with instance manager.
* Update various dependencies.

# Version 1.5.2
* Add 'SECONDARY_ROUTING_PERCENT' for load balancing on an active/active cluster.
* Add connection pooling to the named user configuration.
* Set the 'APPLICATION' session variable correctly.

# Version 1.5.0
* Update the onpremise configuration's approuter.
  * This update fixes an issue with CORS and now allows adding the HanaAnalyticsAdapter as a live connection.
* Switch the onpremise configuration to use basic authentication by default.
* Update dependencies to their latest versions.

# Version 1.4.0
* Remove MDS specific code and rely on the MDSInAQueryLib v1.1.0 instead for InA parsing/plugin and execution.
* Change in the namespace for the base plugin classes from "com.sap.xsahaa.plugin" to "com.sap.mdsja.plugin",
  but the class name of the plugin facade was not changed (e.g. new full name
  "com.sap.mdsja.plugin.QueryNotifierFacade" instead of "com.sap.xsahaa.plugin.QueryNotifierFacade").
* Add logging information using the Simple Logging Facade For Java (SLF4J) API (make logging available on XSA/CF).
* Remove CORS configuration from the HAA. In the on-premise MTAR package, add the CORS configuration
  to the Application Router.
* Add support for a SQL field in the DataSource class used to parse the DataSource field in InA queries.
  It is to avoid losing the SQL field in case a plugin modify the DataSource field.

# Version 0.9.8 / Version 1.0
* Documentation update

# Version 0.9.7
* Allow Instance-based Authorization with DCL (Flag PERSONALIZE\_JWT)
* Allow login as named user (Flag USE\_NAMED\_USER)

# Version 0.9.6
* Disable CSRF Protection.
    * XSa/CF apps need to handle it in their application router.
    * This needed to be disabled in contrast to 0.9.4, as it was enabled in spring 4.1 by default.

# Version 0.9.5
* No binding to hdi-shared container necessary for managed HANA scenarios
* Replaced vulnerable libraries
* Updated to spring-security 4.1

# Version 0.9.4
* Clean-up of dependencies

# Version 0.9.3
* Fixes
  * Fix corrupt war file

# Version 0.9.2
* InstanceManager Support
* Logged-in User is required for every scenario, UAA and Approuter usage recommended for binding to XSa Hana Analytics Adapter

# Version 0.9.1
* Connection to defined HANA using user provided service
* Connection to HDI Container configurable at push time
* LiveConnection from SAP Analytics Cloud using Reverse Proxy
* LiveConnection from SAP Analytics Cloud using DIRECT Connection (CORS Support)
* Trusted CORS Origin configurable at push time
* auth.html file which is required to support XSa UAA in the SAP Analytics Cloud LiveConnection
