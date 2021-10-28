# Pihole DNS app for Splunk

![GitHub](https://img.shields.io/github/license/zachchristensen28/pihole_dns_app)
[![Documentation Status](https://readthedocs.org/projects/splunk-pihole-app-documentation/badge/?version=latest)](https://splunk-pihole-app-documentation.readthedocs.io/en/latest/?badge=latest)

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! https://pi-hole.net/

Info | Description
------|----------
Version | 2.2.1 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole® v5.3.x, FTL 5.8.x](https://pi-hole.net/)

```TEXT
Version 2.2.1

- fixed error in stats command error on Splunk version 8.2.0 - #38
- added version to dashboards to support jQuery v3.5.
- adding new macro (pihole_modinput_index) for modular inputs indexes.
- New Dashboards:
    - Data Overview - Displays license utilization stats.
- Updated Blocklist Activity Dasboard to use new data from modular inputs.
- Added new lookup: pihole_groups_lookup
```

## Documentation

Full documentation can be found at https://splunk-pihole-app-documentation.rtfd.io/

## Bugs/Feature Requests

Please open an issue or submit a feature requests at [github.com](https://github.com/ZachChristensen28/pihole_dns_app/issues)
