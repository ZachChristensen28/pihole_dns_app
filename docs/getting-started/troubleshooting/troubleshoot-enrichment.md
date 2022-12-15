# Troubleshoot Enrichment

## Common Problems

### Permission Issue

The most common problem with not seeing hostnames populated is that the permissions for the lookup file are not correct. Check the following.

1. In Splunk Web, Navigate to Settings > Lookups > Lookup table files.
1. Search for the name of your lookup file.
1. Verify the permissions for the file by clicking "Permissions."
1. Be sure "All apps (system)" is selected.
1. Be sure "Read" permissions is granted to Everyone.

If you are utilizing a lookup definition, perform the same steps for the definition.

### Search Macro Definition

Check the modified [lookup search macros](../../configure/configure-macros/#update-lookup-macros) for accuracy. It may be possible that there is a typo in the changed values. See [Update Macros](../../configure/configure-macros/#update-lookup-macros) in this documentation for more information.