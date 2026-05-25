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

The screenshots show the local input configuration, confirmation that events are being indexed, search filtering by host and source, and dashboard creation.

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

## Screenshots

| Step | Evidence |
| :--- | :--- |
| Splunk Enterprise installation | ![Splunk Enterprise installation](assets/01-splunk-download.png) |
| Select Windows Event Log inputs | ![Select Windows Event Log inputs](assets/02-selecting-inputs.png) |
| Local event log input configured | ![Local event log input configured](assets/03-local-event-log.png) |
| Data input menu | ![Data input menu](assets/04-data-input.png) |
| Confirm logs are searchable | ![Confirm logs are searchable](assets/05-confirming-logs-are-working.png) |
| Narrow search results | ![Narrow search results](assets/06-narrowing-down-the-search.png) |
| Create table view | ![Create table view](assets/07-created-table-view-of-search.png) |
| Create dashboard | ![Create dashboard](assets/08-creating-a-dashboard.png) |
| Add table chart | ![Add table chart](assets/09-adding-a-table-chart.png) |
| Add customized search to table | ![Add customized search to table](assets/10-adding-customized-search-for-table.png) |
| Set dashboard as main dashboard | ![Set dashboard as main dashboard](assets/11-setting-dashboard-as-main-dash-on-home.png) |

## Outcome

By the end of the lab, Splunk was successfully ingesting Windows event logs from the local host. I was able to search Security and Application logs, filter events by `host`, `source`, and `EventCode`, create a table view, and build a Dashboard Studio dashboard to display the filtered results.

## Notes

This was a personal home lab used for learning and portfolio documentation. The screenshots are from a local lab environment and do not contain production system data.
