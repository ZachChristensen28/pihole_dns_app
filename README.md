# Pihole DNS app for Splunk

![GitHub](https://img.shields.io/github/license/zachchristensen28/pihole_dns_app)

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! https://pi-hole.net/

This app was designed with efficiency in mind. It leverages the CIM accelerated data to quickly display the dashboards, no matter the size of your environment. This app works with the [Pihole DNS Add-on](https://splunkbase.splunk.com/app/4506/) add-on which provides the field extractions necessary for this app.

\*\***_NOTICE_**\*\*

Pi-hole® v5 changed the way blocked queries are logged. Download the latest [Pihole DNS Add-on](https://splunkbase.splunk.com/app/4506/) to fix the issue in Splunk.

Info | Description
------|----------
Version | 2.2.0 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole® v5.3.x, FTL 5.8.x](https://pi-hole.net/)
App has a web UI | Yes. This App contains views.

```TEXT
Version 2.2.0

- Made DHCP lookup simplier
- Fixed issue causing DNS search dashboard to not populate from a custom lookup -> #35

```

## Requirements

- Install [Splunk Common Information Model](https://splunkbase.splunk.com/app/1621/)
- Install [Pihole DNS Add-on](https://github.com/ZachChristensen28/TA-pihole_dns) also located on [Splunkbase](https://splunkbase.splunk.com/app/4505/)
- Install [Force Directed App for Splunk](https://splunkbase.splunk.com/app/3767/)
- Install [Status Indicator - Custom Visualizatioin](https://splunkbase.splunk.com/app/3119/)
- (If using DHCP) Enable the "DHCP Leases Lookup" Saved search (see [DHCP Requirement](#dhcp-requirement)).
- (Recommended) Enable Savedsearch `Pihole - Blocklist Lookup - Gen` to map blocked queries to their originating blocklists (see [Blocklist Mapping](#blocklist-mapping)).
- (Recommended) Setup modular inputs on the Pihole DNS Add-on. See the [Modular Input Setup](https://github.com/ZachChristensen28/TA-pihole_dns/wiki/Modular-Input-Setup) wiki for more information.

## Setup

### DHCP Requirement

For DHCP hostname enrichment to work, there are two scheduled searches that need to be enabled (Disabled by default).

Search Name | Description | Default Schedule
----------- | ----------- | ----------------
Pihole - Create DHCP Lease Lookup | Only needs to be run once. This will create the initial lookup for DHCP leases. Defaults to the last 7 days. | None
Pihole - DHCP Leases Lookup - Gen | Recurring search to keep DHCP leases up to date. | Runs Hourly
Pihole - DHCP Remove Old Leases (Optional) | This search will remove leases that have not been updated for a period of time. The default is two weeks. | Once per day

### Blocklist Mapping

**Prerequisite:** The scripted input for the [Pihole DNS Add-on](https://github.com/ZachChristensen28/TA-pihole_dns) must be enabled on the universal forwarder where the Pi-hole server is located.

Update the search macro `pihole_blocklist_index` to the appropriate value. Enable the Savedsearch and update the time of the schedule (if needed).

Search Name | Description | Default Schedule
----------- | ----------- | ----------------
Pihole - Blocklist Lookup - Gen | Populates the `pihole_blocklist_lookup` file. | Once per day at 7:01 AM.

### Update Default Macros

(Recommended) To ensure this App functions efficiently, it is important to update a few search macros. Change the following macros to their appropriate values:

Macro | Default | Description
----- | ------- | -----------
`pihole_index` | index=* | Update to the specific index being used for the "pihole" sourcetype.
`pihole_system_index` | \`pihole_index\` | Update to the specific index being used for the "pihole:system" sourcetype, if different from the main pihole index.
`pihole_dhcp_index` | \`pihole_index\` | Update to the specific index being used for the "pihole:dhcp" sourcetype, if different from the main pihole index.
`pihole_dhcp_lease_retention` | 1209600 | Default retention time (in seconds) for DHCP hosts. Update as needed.
`pihole_blocklist_index` | \`pihole_index\` | Update to the index set in the scripted input from the Pihole DNS Add-on.
`pihole_summariesonly` | summariesonly=false | Defaults to not using summarized data from the CIM. Set to "true" if using data model acceleration.
`pihole_filter_index` | \`pihole_index\` | Update to the specific index being used for the pihole:filters sourcetype created from the filters modular input.

### Enable Data Model Acceleration

Before enabling Data model acceleration, ensure your dns index has been included on the CIM add-on list of indexes. Navigate to Apps > Manage Apps. Find the App "Splunk Common Information Model" and click `set up` on the right side. Select the "Network Resolution" and ensure the index list contains the dns index being used.

Enabling Data model acceleration will enable the searches to perform much more efficiently, however, it is not required. To do this, select Settings > Data Models. Then click "Edit" for the `Network Resolution (DNS)` data model > Click "Edit Acceleration". Then enable the data model acceleration.

Update the `pihole_summariesonly` macro to be "true"

## Bugs/Feature Requests

Please open an issue or submit a feature requests at [github.com](https://github.com/ZachChristensen28/pihole_dns_app/issues)
