# Pihole DNS app for Splunk

Visualize your pihole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome pi-hole server. If not, check it out! https://pi-hole.net/

This app was designed with efficiency in mind. It leverages the CIM accelerated data to quickly display the dashboards, no matter the size of your environment. This app works with the [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) add-on which provides the field extractions necessary for this app.  

Info | Description
------|----------
Version | 2.1.1 - See on [Splunkbase](https://splunkbase.splunk.com/app/4506/)
Vendor Product Version | [Pi-hole v4.3.2](https://pi-hole.net/)
App has a web UI | Yes. This App contains views.

```
Version 2.1.1
- Updated README
- Updated visualizations to no longer required Data models to be accelerated to function.
```

## Requirements

- Install [Splunk Common Information Model](https://splunkbase.splunk.com/app/1621/)
- Install [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) also located on [Splunkbase](https://splunkbase.splunk.com/app/4505/)
- Install [Force Directed App for Splunk](https://splunkbase.splunk.com/app/3767/)

## Setup

To ensure this App functions efficiently, it is important to update a few variables.

### Update Default Macro

This app ships with the \`pihole_index\` macro. The default behavior is `index=*`. It is recommended to update this macro to search the appropriate index.

This can be done from the web interface by first navigating to the Pihole DNS App. Then Select at the top Settings > Advanced Search > Search macros (Make sure the Pihole app is selected in the App dropdown menu). Click the `pihole_index` macro and update as necessary.

### Enable Data Model Acceleration

Before enabling Data model acceleration, ensure your dns index has been whitelisted on the CIM add-on. Navigate to Apps > Manage Apps. Find the App "Splunk Common Information Model" and click `set up` on the right side. Select the "Network Resolution" and ensure the `indexes whitelist` contain the dns index being used.

Enabling Data model acceleration will enable the searches to perform much more efficiently. To do this, select Settings > Data Models. Then click "Edit" for the `Network Resolution (DNS)` data model > Click "Edit Acceleration". Then enable the data model acceleration.
