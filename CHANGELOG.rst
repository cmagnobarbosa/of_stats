#########
Changelog
#########

All notable changes to the ``of_stats`` project will be documented in this file.

[UNRELEASED] - Under development
********************************
Added
=====

Changed
=======

Deprecated
==========

Removed
=======

Fixed
=====

Security
========

Changed
=======


[2.0] - 2021-04-22
******************
Added
=====
- Added support for automated tests and CI with Travis.

Changed
=======
- Replaced RRDtool by ``kytos/kronos`` to persist the statistics.
- Refactored ``AggregateStats``, ``FlowStats`` and ``PortStats`` class
  to use ``kytos/kronos`` to save data.
- Updated ``requirements.txt`` file.
- Moved unit tests to ``tests/unit`` dir.
- Changed ``setup.py`` to catch exception for linter error.
- Updated OpenAPI and ``README.rst`` file.
- Added ``kytos/kronos`` as dependency.
- Yala substitutes Pylama as the main linter checker.
- Changed README.rst to include some info badges.

Removed
=======
- Removed RRDtool dependencies.

Fixed
=====
- Fixed ``user_speed`` unit test.
- Fixed ``setup.py`` changing it to one inspired by ``of_core``.
- Fixed linter issues.
- Enable ``of_stats`` in Scrutinizer.


[1.1.0] - 2018-04-20
********************
Added
=====
- Add speed to port statistics.
- Multipart requests for switches with OpenFlow 1.3.
- Use flow factory.
- Add support for OF 0x04 (1.3).

Changed
=======
- Adapt the NApp to changes in python-openflow.
- Get stats updates from OF1.3 switches.
- Update user_speed to bytes.
- Move tests to tests folder.
- Update controller's custom interface speed.
- Update OpenAPI.
- Standardize interface speed value.
- Return 30 points instead of 60.
- Get latest 30 points instead of whole BD period.
- Update v0x04 body_type to multipart_type.
- Update RRD creation time steps.
- Use generic flow.
- Add /random for random port statistics.
- Update controller's interface stats.
- Update controller's flow.stats.

Fixed
=====
- Fix retrieve flows error.
- Fix exception when disabling NApp.
- Fix RRD-not-found reply.
- Fix bug when switch has no speed.

[1.0.0] - 2017-11-30
********************
Added
=====
- Use new generic Flow from of_core.
- Create Rest API in openapi.yml.
- Use rest decorator in of_stats.
- Adding dependency of `kytos/of_core` in kytos.json.
- include __init__ files in version specific of_core utils modules.

[0.4.0] - 2017-06-16
********************
Added
=====
- Experimental OpenFlow 1.3 support in of_core.
- Examples of requests/replies to of_flow_manager REST endpoints.

Changed
=======
- of_core is now responsible for ALL basic OpenFlow packet handling, previously
  done by Kytos.
- of_flow_manager REST API endpoints and JSON input/output.
- Updated NApps documentation.
- Updated requirements for of_stats.
- of_lldp now ignores lldp packets generated by other applications.
- switch 'lastseen' information is now updated on every new openflow message
  received.

Fixed
=====
- of_topology will no more detect inexistent hosts if the topology has multiple
  switches.
- Several bug fixes.

[0.3.0] - 2017-05-05
********************
Added
=====
- Individual requirements.txt file for NApps.
- Continuous integration with Code Quality Score and test coverage.

Changed
=======
- Installation process of NApps.
- Updated documentation content and templates.
- NApp imports on Kytos now grants easier access to some classes.
- Travis CI replaced by Scrutinizer.
- Logging updated to match changes on Kytos project.
- Updated requirements and dependencies.

Deprecated
==========
- 'author' attribute was renamed to 'username', and will be removed in future
  releases.

Removed
=======
- Installing from source. Now it works only in develop mode. Otherwise,
  kytos-utils shall be used.
- 'long_description' JSON attribute from kytos.json for all NApps. description
  shall be short, and details shall be provided in the README file.

Fixed
=====
- of_core NApp protocol negotiation reviewed to handle correctly Hello, Echo,
  FeaturesRequest and StatsRequest packets.
- Several bug fixes.


[0.2.0] - 2017-03-24
********************
Added
=====
- Python3.6 requirement.
- NApps now can import from other NApps.
- Individual Settings file for NApps.
- Individual documentation for NApps.
- Description field for registered switches.

Changed
=======
- Improved installing process.
- Directory structure of installed/enabled NApps.
- Uptated overall project documentation.
- Updated all Napps metadata.
- of.ipv6disable renamed to of_ipv6drop.
- Updated NApps requirements and dependencies.
- Correct handling of Port Status changes.
- of_stats now supports various link/port speeds in the topology, including
  user-defined.

Deprecated
==========
- Kyco (Kytos Controller) is now called Kytos - every reference was updated to
  match the change.
- Core NApps are now called Kytos NApps.

Removed
=======
- of_liveness NApp.

Fixed
=====
- Tests, coverage and style checks corrected.
- Logger names for NApps.
- Event names corrected to match NApp names.
- NApp names corrected, without dashes or dots.
- Includes all flows and interfaces in the topology, even unused ones.
- Many bug fixes.


[0.1.0] - 2016-11-09
********************
Added
=====
- of.web.topology.layout NApp - Application to manage topology layout on the
  web interface.
- Topology endpoint returning a JSON file with nodes and links.
- A REST API for of.stats NApp.
- of.stats NApp - Collects network statistics and stores it for visualization.
- of.flow_manager NApp - Application to register REST endpoints to manage flows.
- of.lldp NApp - Discovers network topology using Link Layer Discovery Protocol.
- of.ipv6disable NApp - Simple application to disable IPv6 traffic on the
  network.
- kytos.json file with NApp metadata for every NApp.
- of.l2lsloop NApp - An L2 learning switch supporting loops (experimental).
- of.l2ls NApp - An L2 learning switch.
- LICENSE file.
- Pep8 compliance.
- TRAVIS-CI tests and coverage.
- Logging support.
- Setup file compatible with Python Virtual Environment.
- Documentation.
- First Core NApps.

Changed
=======
- Updated requirements for NApps.
- NApps now have a method which will loop itself over intervals.
- of.core NApp totally refactored:

  - Now handles Packet-in messages and generates events correclty.
  - Updates interfaces of switches when receiving features-replies.
  - Updates flows using Flow Stats Request messages.

- Improved NApp installing process.
- Participation of NApps in the handshake process.

Fixed
=====
- Logs for NApps: of.liveness, of.core
- Many bug fixes.
