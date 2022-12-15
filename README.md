# Pihole DNS app for Splunk

![GitHub](https://img.shields.io/github/license/zachchristensen28/pihole_dns_app)
[![docs](https://github.com/ZachChristensen28/pihole_dns_app/actions/workflows/deploy-docs.yml/badge.svg)](https://splunk-pihole.ztsplunker.com/)
[![Splunk Appinspect](https://github.com/ZachChristensen28/pihole_dns_app/actions/workflows/appinspect.yml/badge.svg)](https://github.com/ZachChristensen28/pihole_dns_app/actions/workflows/appinspect.yml)
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/ZachChristensen28/TA-pihole_dns)](https://github.com/ZachChristensen28/pihole_dns_app/releases)
[![Splunkbase App](https://img.shields.io/badge/Splunkbase-pihole__dns__app-blue)](https://splunkbase.splunk.com/app/4506/)

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! https://pi-hole.net/

## Documentation

Full documentation can be found at https://splunk-pihole.ztsplunker.com/

## About

Info | Description
------|----------
Version | 2.2.2 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole® v5.x, FTL 5.x](https://pi-hole.net/)

```TEXT
Version 2.2.2

- Updated search dasboard to allow filtering of pie charts based of query input.
- Deprecating all knowledge objects for blocklist activity. This feature will be brought back with v6 of Pi-hole.
- Added ability to search by host in dashbaords.
- Transaction search dashboard will now show if the CNAME was blocked.
```

__*Disclaimer*__

*This Splunk app is __not__ affiliated with* [**Pi-hole**®](https://pi-hole.net) *and is not sponsored or sanctioned by the Pi-hole® team. As such, the included documentation does not contain information on how to get started with the Pi-hole DNS server. Rather, this documentation serves as a guide to help visualize the data in Splunk. Please visit [https://pi-hole.net](https://pi-hole.net) for documentation on installing/configuring your own Pi-hole server.*

Pi-hole is and the Pi-hole logo are [registered trademarks](https://pi-hole.net/trademark-rules-and-brand-guidelines/) of Pi-hole LLC.

## Bugs/Feature Requests

Please open an issue or submit a feature requests at [github.com](https://github.com/ZachChristensen28/pihole_dns_app/issues)
