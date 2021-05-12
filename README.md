# Pihole DNS app for Splunk

![GitHub](https://img.shields.io/github/license/zachchristensen28/pihole_dns_app)
[![Documentation Status](https://readthedocs.org/projects/splunk-pihole-app-documentation/badge/?version=latest)](https://splunk-pihole-app-documentation.readthedocs.io/en/latest/?badge=latest)

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! https://pi-hole.net

Info | Description
------|----------
Version | 2.1.9 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole® v5.3.x, FTL 5.8.x](https://pi-hole.net/)
App has a web UI | Yes. This App contains views.

```TEXT
Version 2.1.9

New
- Macro added for filter index.
- Created new view "Pihole Filters." This dashboard displays the regex and exact filters created in the Pi-hole server. This requires modular inputs to be setup on the Pihole DNS add-on.
- Created new view "Filter Tester." This dashboard will help test regex and exact filters before you implement them on the Pi-hole.
```

## Documentation

Full documentation can be found at https://splunk-pihole-app-documentation.rtfd.io/

## Bugs/Feature Requests

Please open an issue or submit a feature requests at [github.com](https://github.com/ZachChristensen28/pihole_dns_app/issues)
