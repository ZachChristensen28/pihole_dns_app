# Update Search Macros

!!! info "Recommended Step"

To ensure this App functions efficiently, it is important to update a few search macros. Change the following macros to their appropriate values. For more information on the search macros used in this app, see [Search Macros Reference](../../reference/reference-macros.md).

## How to Update Macros

1. Open the Pihole DNS app for Splunk.
1. Navigate to Settings > Advanced Search > Search macros.

    ??? question "Not seeing any results"
        If no results are found, be sure that the "App" context is set to the Pihole DNS app, owner is set to "Any", and choose "Created in the App" from the remaining drop-down.

1. Update the search macros as necessary.

## Update Index Macros

Update the index specific macros to the indexes being used for the Pi-hole data. Updating these to the correct values will increase performance of searches.

Macro | Default | Description | Example Value
----- | ------- | ----------- | -------------
pihole_index | index=* | Update to the specific index being used for the "pihole" sourcetype. | `index=dns`
pihole_dhcp_index | \`pihole_index\` | Update to the specific index being used for the "pihole:dhcp" sourcetype, if different from the main pihole index. | `index=dhcp`
pihole_blocklist_index | \`pihole_index\` | Update to the index set in the scripted input from the Pihole DNS Add-on. | `index=dns_system`
pihole_system_index | \`pihole_index\` | Update to the specific index being used for the "pihole:system" sourcetype created from the system summary events modular input. see [Pihole Add-on: Modular Inputs](https://splunk-pihole-ta-documentation.rtfd.io/en/latest/getting-started/configure-inputs/configure-modinput/). | `index=dns_system`
pihole_filter_index | \`pihole_index\` | Update to the specific index being used for the pihole:filters sourcetype created from the filters modular input. see [Pihole Add-on: Modular Inputs](https://splunk-pihole-ta-documentation.rtfd.io/en/latest/getting-started/configure-inputs/configure-modinput/). | `index=dns_system`

## Update Search Related Macros

Update this search macro **only** if you are using DMA. see [Configure Data Model Acceleration](configure-dma.md) for more information.

!!! warning
    Updating this macro to "true" without first enabling data model acceleration will cause the searches in dashboards to fail or have no results.

Macro | Default | Description | Example Value
----- | ------- | ----------- | -------------
pihole_summariesonly | summariesonly=false | Defaults to not using summarized data from the CIM. Set to "true" if using data model acceleration. | `summariesonly=true`

## Update Lookup Macros

Update the following search macros if you are utilizing a custom lookup for hostname enrichment. If you are using the default lookup included in this app, **do not** modify the following. see [Configure Enrichment](configure-enrichment.md) for more information.

Macro | Default | Description | Example Value
----- | ------- | ----------- | -------------
pihole_host_lookup_name | pihole_dhcp_lease_lookup | Update to the name of the CSV file you are using. | `my_pihole_lookup.csv`
pihole_lookup_field_ip | dest_ip | Update only if you are not using the default field for IPs. | `client_ip`
pihole_lookup_field_hostname | dest_nt_host | Update only if you are not using the default field for hostnames | `client_name`
pihole_lookup_field_mac | dest_mac | Update only if you are not using the default field for mac addresses. | `client_mac`

## Troubleshooting

After saving the search macros, navigate back to the Pihole DNS app and you should now see the "Hostname" field being populated. If not, see [Troubleshooting Enrichment](../troubleshooting/troubleshoot-enrichment.md).

--8<-- "includes/abbreviations.md"