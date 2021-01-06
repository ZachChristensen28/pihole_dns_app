# Pihole DNS app for Splunk

![GitHub](https://img.shields.io/github/license/zachchristensen28/pihole_dns_app)

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! https://pi-hole.net/

This app was designed with efficiency in mind. It leverages the CIM accelerated data to quickly display the dashboards, no matter the size of your environment. This app works with the [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) add-on which provides the field extractions necessary for this app.

\*\***_NOTICE_**\*\*

Pi-hole® v5 changed the way blocked queries are logged. Download the latest [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) to fix the issue in Splunk.

Info | Description
------|----------
Version | 2.1.6 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole® v5.2.x, FTL 5.3.x](https://pi-hole.net/)
App has a web UI | Yes. This App contains views.

```TEXT
Version 2.1.6

New
- Added dropdown on the Pihole DNS search dashboard populated by DHCP entries #18 (@mljdivemaster)
- Added ability to filter by Pi-hole in dashboards #17
- Added macro to control summary indexes when utilizing tstats
- Added Top Queries Allowed/Blocked by Source on the Pihole DNS search Dashboard

Updated
- Updated the Pihole DNS search dashboard table to reduce the amount of "unknown" values.
- Updated the Pihole Query Log dashboard table to reduce the amount of "unknown" values. Also, updated field names for clarity.

Fixed
- Fixed Typos in token on the Pihole DNS search dashboard.
- Fixed search on the Pihole Transaction dashboard which prevented no information to display on the force directed panel.
```

## Requirements

- Install [Splunk Common Information Model](https://splunkbase.splunk.com/app/1621/)
- Install [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) also located on [Splunkbase](https://splunkbase.splunk.com/app/4505/)
- Install [Force Directed App for Splunk](https://splunkbase.splunk.com/app/3767/)
- Install [Status Indicator - Custom Visualizatioin](https://splunkbase.splunk.com/app/3119/)
- (If using DHCP) Enable the "DHCP Leases Lookup" Saved search ([See DHCP Requirement](#dhcp-requirement)).

## Setup

### DHCP Requirement

For DHCP hostname enrichment to work, there are two scheduled searches that need to be enabled (Disabled by default).

Search Name | Description | Default Schedule
----------- | ----------- | ----------------
Pihole - Create DHCP Lease Lookup | Only needs to be run once. This will create the initial lookup for DHCP leases. Defaults to the last 7 days. | None
Pihole - DHCP Leases Lookup - Gen | Recurring search to keep DHCP leases up to date. | Runs Hourly
Pihole - DHCP Remove Old Leases (Optional) | This search will remove leases that have not been updated for a period of time. The default is two weeks. | Once per day

### Update Default Macros

(Recommended) To ensure this App functions efficiently, it is important to update a few search macros. Change the following macros to their appropriate values:

Macro | Default | Description
----- | ------- | -----------
`pihole_index` | index=* | Update to the specific index being used for the "pihole" sourcetype.
`pihole_system_index` | \`pihole_index\` | Update to the specific index being used for the "pihole:system" sourcetype, if different from the main pihole index.
`pihole_dhcp_index` | \`pihole_index\` | Update to the specific index being used for the "pihole:dhcp" sourcetype, if different from the main pihole index.
`pihole_dhcp_lease_retention` | 1209600 | Default retention time (in seconds) for DHCP hosts. Update as needed.
`pihole_summariesonly` | summariesonly=false | Defaults to not using summarized data from the CIM. Set to "true" if using data model acceleration.

### Enable Data Model Acceleration

Before enabling Data model acceleration, ensure your dns index has been included on the CIM add-on list of indexes. Navigate to Apps > Manage Apps. Find the App "Splunk Common Information Model" and click `set up` on the right side. Select the "Network Resolution" and ensure the index list contains the dns index being used.

Enabling Data model acceleration will enable the searches to perform much more efficiently, however, it is not required. To do this, select Settings > Data Models. Then click "Edit" for the `Network Resolution (DNS)` data model > Click "Edit Acceleration". Then enable the data model acceleration.

Update the `pihole_summariesonly` macro to be "true"

## Bugs/Feature Requests

Please open an issue or submit a feature requests at [github.com](https://github.com/ZachChristensen28/pihole_dns_app)

## Versions

```TEXT
Version 2.1.5
New:
- Updated Pihole Overview dashboard to include data from the modular input of the TA-pihole_dns add-on.
Fixed:
- Updated DHCP enrichment macro to be simpler.

Version 2.1.4
Fixed
- Fixed incomplete eval statement on Query log dashboard causing the "Host" field to be missing.
- Fixed missing "Transaction ID" field on Query log dashbaord

Version 2.1.3
- Added DHCP Overview Dashboard.
- If DHCP is being used, IP address will be enriched with hostnames.
- Added select enhancements to dashboards.

* New requirement added for Status Indicator - Custom Visualization.
* New requirement for populating DHCP hostnames (if DHCP is being used).

Note: Download the latest Pihole add-on for the new dashboards to work (see Requirements).
Version 2.1.2
- Fixed Broken Drilldown on DNS Search Page.

Version 2.1.1
- Updated README
- Updated visualizations to no longer required Data models to be accelerated to function.
```
