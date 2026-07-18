# Splunk: The Basics

**Room:** Splunk: The Basics
**Category:** SOC / Security Operations Center
**Platform:** TryHackMe

---

## Learning Objectives

- Understand the components of Splunk
- Explore some available options in Splunk
- Understand log ingestion in Splunk
- Practically ingest some logs and analyze them

---

## Connecting to the Lab

The lab is accessed through the Splunk web interface — the Splunk Enterprise website — where all searching, dashboarding, and data management happens.

---

## Splunk Components

Splunk's architecture is built around three core components:

- **Forwarder** — a lightweight agent installed on source systems that collects and forwards raw log data to the indexer
- **Indexer** — receives data from forwarders, processes it, and stores it in a searchable, indexed format
- **Search Head** — the interface analysts use to run searches and queries against the indexed data, and where dashboards and visualizations are built

---

## Navigating Splunk

- **Splunk Bar** — the top navigation bar for moving between apps and core functions
- **App Panel** — where installed Splunk apps are listed and launched
- **Splunk Dashboard** — the customizable landing view showing saved searches, panels, and visualizations for at-a-glance monitoring

---

## Adding Data — A Practical Approach

Splunk's "Add Data" workflow follows a simple guided process:

1. **Select Source** — choose where the data is coming from (file upload, monitor, forwarder, etc.)
2. **Input Settings** — configure how the data should be indexed (source type, index destination, host field)
3. **Review** — confirm all the configured settings before committing
4. **Done** — data ingestion begins and the source becomes searchable

### Useful Checks

After ingestion, it's worth verifying that the data landed correctly — checking the source type was parsed as expected, timestamps extracted properly, and the expected index/host fields are populated before relying on the data for analysis.

---

## Lab Investigation

The lab task involved ingesting a `vpn.log` file and analyzing it within Splunk to answer investigative questions:

- Finding the event logs associated with a user named **Melena**
- Identifying the **username** associated with a specific IP address in the log data

---

## Conclusion

Splunk's forwarder → indexer → search head pipeline is the foundation of how logs get from source systems into a searchable, analyzable format. Walking through the "Add Data" workflow and then querying real ingested log data (like the VPN logs in this room) builds the practical skill of turning raw logs into answers — tracing a username back to an IP, or isolating a specific user's activity — which is exactly the kind of task a SOC analyst performs during an investigation.
