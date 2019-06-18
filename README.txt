#Pihole DNS app for Splunk
Visualize your pihole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome pi-hole server. If not, check it out! https://pi-hole.net/

This app was designed with efficiency in mind. It leverages the CIM accelerated data to quickly display the dashboards, no matter the size of your environment. This app works with the [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns) add-on which provides the field extractions necessary for this app.

```
Version: 2.1.0
```

## Requirements
- Install [Splunk Common Information Model](https://splunkbase.splunk.com/app/1621/)
  - Network Resolution Datamodel must be Accelerated for the dashboards to function.
- Install [TA-pihole_dns](https://github.com/ZachChristensen28/TA-pihole_dns)
- Install [Force Directed App for Splunk](https://splunkbase.splunk.com/app/3767/)

## Configurations
There is one search macro that needs to be modified to improve performance. Update the \`pihole_index\` macro to the appropriate index. This can be done from the web interface by first navigating to the Pihole DNS App. Then Select at the top Settings > Advanced Search > Search macros. (Make sure the Pihole app is selected).
