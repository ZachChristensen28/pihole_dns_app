# Data Model Acceleration

!!! info "Optional Step"

Enabling Data model acceleration (DMA) will allow the searches to perform much more efficiently for larger datasets. If you run into issues with dashboards taking too long to load, data model acceleration will increase performance with a slight increase to resource usage. To learn more about data model acceleration see [Splunk Docs: Accelerate data models](https://docs.splunk.com/Documentation/Splunk/latest/Knowledge/Acceleratedatamodels).

## Enable Acceleration

Before enabling Data model acceleration, ensure your dns index has been allowed on the CIM add-on list of indexes. 

1. In Splunk web, Navigate to Apps > Manage Apps. 
1. Find the App "Splunk Common Information Model" and click `set up` on the right side. 
1. Select the "Network Resolution" data model.
1. Enter the name of the index being used for the pihole data in the "Indexes whitelist" field. This will allow only the indexes listed to be accelerated. If you are ingesting DNS data into other indexes and also want them to be included in the acceleration, list them here as well.

    ???+ tip
        To quickly identify which indexes are being used for this data model, the following query can be run:

        ```text
        | tstats count from datamodel=Network_Resolution.DNS where index=* by index
        ```

1. Once the appropriate indexes are listed, check the "Accelerate" box at the top and save.
1. The data model will begin to build. This may take some time depending on the size.
1. Update the `pihole_summariesonly` macro to "summariesonly=true". Setting this will force the dashboards to use accelerated data only, optimizing the searches. see [Update Macros](../configure-macros/#update-search-related-macros) in this documentation for more information.

--8<-- "includes/abbreviations.md"