# Splunk Windows Event Log Home Lab

## Overview

This home lab documents the installation and configuration of Splunk Enterprise for local Windows Event Log collection. The goal of the lab was to confirm that Windows Security, Application, and System logs were being ingested, then use SPL searches and Dashboard Studio to build a simple dashboard for reviewing clear log related activity.

Video walkthrough:
https://www.youtube.com/watch?v=3CiRs6WaWaU&list=PLlIr0D2kbUZODythCTlQ0JMbO8bigYO6P&index=10

## Lab objective

* Install Splunk Enterprise in a local Windows lab environment.
* Configure local Windows Event Log inputs.
* Ingest Application, Security, and System logs.
* Validate that events are searchable in Splunk.
* Narrow searches by host, source, and EventCode.
* Create a dashboard and table visualization for log review.
* Set the custom dashboard as the main home dashboard.

## Tools and technologies

* Splunk Enterprise
* Windows Event Logs
* SPL, Search Processing Language
* Splunk Dashboard Studio
* Local Windows host named `Dakotah-DT`

## Configuration summary

The lab used Splunk local event log collection to ingest Windows logs from the local machine. The selected logs were:

* Application
* Security
* System

The lab evidence shows the local input configuration, confirmation that events are being indexed, search filtering by host and source, and dashboard creation.

## Example searches used

```spl
*
```

```spl
host="Dakotah-DT" source="WinEventLog:Security" EventCode=5379
```

The filtered Security log search focused on Windows Event ID `5379`, which appeared in the lab data with the message `Credential Manager credentials were read.`

## What I practiced

* Installing Splunk Enterprise locally.
* Selecting Windows Event Logs as a Splunk data input.
* Confirming successful data ingestion.
* Reading Windows event metadata such as `host`, `source`, `sourcetype`, `EventCode`, `LogName`, and `_time`.
* Filtering security events with SPL.
* Creating a table view from search results.
* Building a basic dashboard panel for monitoring.
* Setting a custom Splunk dashboard as the home dashboard.

## Screenshot evidence captured

* Splunk Enterprise installation.
* Selecting Windows Event Log inputs.
* Local event log input configuration.
* Data input menu.
* Confirming logs are searchable.
* Narrowing down the search results.
* Creating a table view from the search.
* Creating the dashboard.
* Adding a table chart.
* Adding a customized SPL search to the table.
* Setting the custom dashboard as the main home dashboard.

## Outcome

By the end of the lab, Splunk was successfully ingesting Windows event logs from the local host. I was able to search Security and Application logs, filter events by `host`, `source`, and `EventCode`, create a table view, and build a Dashboard Studio dashboard to display the filtered results.

## Notes

This was a personal home lab used for learning and portfolio documentation. The screenshots are from a local lab environment and do not contain production system data.
