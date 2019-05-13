# Pihole DNS app for Splunk
Visualize your pihole in Splunk! If you've landed on this app, it's probably because you are running your own super awesome pi-hole server. If not, check it out! https://pi-hole.net/

This app was designed with efficiency in mind. It leverages the CIM accelerated data to quickly display the dashboards, no matter the size of your environment. This app works with the TA-pihole_dns add-on which provides the field extractions necessary for this app.  

## Requirements
- [Splunk Common Information Model](https://splunkbase.splunk.com/app/1621/)
  - Network Resolution Datamodel must be Accelerated for the dashboards to function.
- [TA-pihole_dns installed](https://github.com/ZachChristensen28/TA-pihole_dns)
