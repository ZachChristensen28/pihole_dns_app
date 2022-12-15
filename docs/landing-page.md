---
ᴴₒᴴₒᴴₒ: true
hide:
    - navigation
    - toc
---
# Home

!!! quote ""
    __*Disclaimer*__

    *This Splunk app is __not__ affiliated with* [__Pi-hole__®](https://pi-hole.net) *and is not sponsored or sanctioned by the Pi-hole® team. As such, the included documentation does not contain information on how to get started with the Pi-hole DNS server. Rather, this documentation serves as a guide to help visualize the data in Splunk. Please visit [https://pi-hole.net](https://pi-hole.net) for documentation on installing/configuring your own Pi-hole server.*

    Pi-hole is and the Pi-hole logo are [registered trademarks](https://pi-hole.net/trademark-rules-and-brand-guidelines/) of Pi-hole LLC.

Visualize your Pi-hole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome Pi-hole® server. If not, check it out! [https://pi-hole.net/](https://pi-hole.net/)

This app works with the [Pihole DNS Add-on](https://splunkbase.splunk.com/app/4505/) add-on which provides the field extractions necessary for this app.

## Key Features

* Allows for easier troubleshooting of blocked queries.
* Prebuilt dashboards that allows you to drill-down to specific queries for further analysis.
* View daily trends and easily identify if queries are outside the month's norm.
* Test Regex filters before applying them on the Pi-hole server.
* View a list of all DHCP clients.
* Identify errors that may be a result of a misconfiguration.
* Check the DNS queries across all Pi-hole instances in a single place.
* View Allow and Deny filters setup across all Pi-hole servers.
* and more!

## Assumptions

This documentation assumes the following:

1. You have a working Pi-hole server.
2. You have a working Splunk environment.
3. Basic understanding of Splunk and Pi-hole.
4. The [Pihole DNS Add-on for Splunk](https://splunkbase.splunk.com/app/4505) has been installed and configured.

## About

See [Release Notes](reference/releases) for version specific information.

Info | Description
---- | -----------
Version | 2.2.2 - [Splunkbase](https://splunkbase.splunk.com/app/4506) \| [GitHub](https://github.com/ZachChristensen28/pihole_dns_app)
Vendor Product Version | [Pi-hole® 5.x, FTL 5.x](https://pi-hole.net/)

[Get Started](getting-started/app-dependencies/){ .md-button .md-button--primary }
