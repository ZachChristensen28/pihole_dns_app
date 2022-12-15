# Where to Install

## Standalone Deployments

Install this app to the single instance. For more information see [Splunk Docs: Install add-on in a single-instance Splunk deployment](https://docs.splunk.com/Documentation/AddOns/released/Overview/Singleserverinstall)

## Distributed Deployments

Splunk Instance type | Supported | Required | Comments
-------------------- | --------- | -------- | --------
Search Heads | Yes | Yes | Install this app on search heads.
Indexers | No | No | This app does not require installation on indexers.
Heavy Forwarders | No | No | There is no need to install this app on Heavy Forwarders.
Universal Forwarders | No | No | This app should not be installed on Universal Forwarders.

The installation steps for deploying Apps/add-ons in a distributed environment can be found at [Splunk Docs: Install an add-on in a distributed Splunk deployment](https://docs.splunk.com/Documentation/AddOns/released/Overview/Distributedinstall)
