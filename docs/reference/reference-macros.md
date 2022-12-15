# Search Macro Reference

Macro | Default | Description
----- | ------- | -----------
pihole_index | index=* | Update to the specific index being used for the "pihole" sourcetype.
pihole_dhcp_index | \`pihole_index\` | Update to the specific index being used for the "pihole:dhcp" sourcetype, if different from the main pihole index.
pihole_blocklist_index | \`pihole_index\` | Update to the index set in the scripted input from the Pihole DNS Add-on.
pihole_system_index | \`pihole_index\` | Update to the specific index being used for the "pihole:system" sourcetype created from the system summary events modular input. see [Pihole Add-on: Modular Inputs](https://splunk-pihole-ta-documentation.rtfd.io/en/latest/getting-started/configure-inputs/configure-modinput/).
pihole_filter_index | \`pihole_index\` | Update to the specific index being used for the pihole:filters sourcetype created from the filters modular input. see [Pihole Add-on: Modular Inputs](https://splunk-pihole-ta-documentation.rtfd.io/en/latest/getting-started/configure-inputs/configure-modinput/).
pihole_summariesonly | summariesonly=false | Defaults to not using summarized data from the CIM. Set to "true" if using data model acceleration.
pihole_host_lookup_name | pihole_dhcp_lease_lookup | Default Lookup used to map IPs to hostnames.
pihole_lookup_field_ip | dest_ip | Default ip field for the lookup to map IPs to hostnames.
pihole_lookup_field_hostname | dest_nt_hostname | Default hostname field for the lookup to map IPs to hostnames.
pihole_lookup_field_mac | dest_mac | Default mac field for the lookup to map IPs to hostnames.
pihole_enrich_rename | rename \`pihole_lookup_field_hostname\` as "dest_nt_host", \`pihole_lookup_field_ip\` as "dest_ip" | Used by app to rename lookup fields.
pihole_enrich_hostname(1) | lookup \`pihole_host_lookup_name\` \`pihole_lookup_field_ip\` as "$ip_field$" OUTPUTNEW \`pihole_lookup_field_hostname\` as Hostname | Used by app to enrich data with hostnames.
pihole_enrich_blocklist(1) | lookup pihole_blocklist_lookup domain as "$domain_field$" OUTPUTNEW blocklist | Used by app to enrich data with blocklist used.

