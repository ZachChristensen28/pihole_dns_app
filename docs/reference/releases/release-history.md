# Release history for the Pi-hole DNS app for Splunk

The latest version of the Pi-hole DNS app for Splunk is version 2.2.2. See [Release notes for the Pi-hole DNS app for Splunk](../../releases/) of the latest version.

## v2.2.1 <small>June 7, 2021</small>

- Fixed error in stats command error on Splunk version 8.2.0 - [#38](https://github.com/ZachChristensen28/pihole_dns_app/issues/38)
- added version to dashboards to support jQuery v3.5

## v2.2.0 <small>May 12, 2021</small>

- Fixed issue causing DNS search dashboard to not populate from a custom lookup -> [#35](https://github.com/ZachChristensen28/pihole_dns_app/issues/35)
- Made DHCP lookup simpiler and removed excess saved searches related to the DHCP lookup.

## v2.1.9 <small>April 28, 2021</small>

- Added macro for filter index.
- Created new view "Pihole Filters." This dashboard displays the regex and exact filters created in the Pi-hole server. This requires modular inputs to be setup on the Pihole DNS add-on. see [Pihole Add-on: Modular Inputs](https://splunk-pihole-ta-documentation.rtfd.io/en/latest/getting-started/configure-inputs/configure-modinput/) for more information.
- Created new view "Filter Tester." This dashboard will help test regex and exact filters before you implement them on the Pi-hole.

## v2.1.8 <small>Feb 21, 2021</small>

- Removed spaces from `pihole_summariesonly` search macro causing dashboards to have the error "Error in 'tstats' command: Option '=' is invalid." (Introduced in Version 2.1.6) - [#31](https://github.com/ZachChristensen28/pihole_dns_app/issues/31)
- Added ability to see which lists a blocked query belongs to. This requires version 1.2.8 or later of the Pihole DNS Add-on.
- Added Default value on Pihole Overview dashboard for API host selection.

## v2.1.7 <small>Feb 20, 2021</small>

- Added ability to see which lists a blocked query belongs to. This requires version 1.2.8 or later of the Pihole DNS Add-on.
- Added Default value on Pihole Overview dashboard for API host selection.

## v2.1.6 <small>Jan 26, 2021</small>

- Added dropdown on the Pihole DNS search dashboard populated by DHCP entries [#18](https://github.com/ZachChristensen28/pihole_dns_app/issues/18) [(@mljdivemaster)](https://github.com/mljdivemaster)
- Added ability to filter by Pi-hole in dashboards [#17](https://github.com/ZachChristensen28/pihole_dns_app/issues/17)
- Added macro to control summary indexes when utilizing tstats
- Added Top Queries Allowed/Blocked by Source on the Pihole DNS search Dashboard
- Updated the Pihole DNS search dashboard table to reduce the amount of "unknown" values.
- Updated the Pihole Query Log dashboard table to reduce the amount of "unknown" values. Also, updated field names for clarity.
- Fixed Typos in token on the Pihole DNS search dashboard.
- Fixed search on the Pihole Transaction dashboard which prevented no information to display on the force directed panel.

## v2.1.5 <small>Dec 21, 2020</small>

- Updated Pihole Overview dashboard to include data from the modular input of the TA-pihole_dns add-on.
- Updated DHCP enrichment macro to be simpler.

## v2.1.4 <small>Oct 31, 2020</small>

- Incomplete eval statement on Query log dashboard causing the "Host" field to be missing.
- Missing "Transaction ID" field on Query log dashbaord

## v2.1.3 <small>Sept 1, 2020</small>

- Added DHCP Overview Dashboard.
- If DHCP is being used, IP address will be enriched with hostnames.
- Added select enhancements to dashboards.
- New requirement added for Status Indicator - Custom Visualization.
- New requirement for populating DHCP hostnames (if DHCP is being used).

## v2.1.2 <small>July 27, 2020</small>

- Fixed broken Drilldown on DNS Search Dashboard.
