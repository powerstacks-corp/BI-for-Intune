---
hide:
  - toc
  - navigation
---

<div class="hero-banner">
  <h1>BI for Intune <span class="hero-accent">Documentation</span></h1>
  <p>Comprehensive Power BI reporting for Microsoft Intune.</p>
</div>

<div class="quick-links">
  <a class="quick-link-card" href="guides/install-bi-for-intune/">
    <span class="card-icon">
      <img src="images/icon-overview.svg" alt="" class="skip-lightbox">
    </span>
    <span class="card-content">
      <span class="card-label">GETTING STARTED</span>
      <span class="card-title">Setup Guide</span>
    </span>
  </a>
  <a class="quick-link-card" href="guides/create-azure-ad-app-registration/">
    <span class="card-icon">
      <img src="images/icon-how-to-guide.svg" alt="" class="skip-lightbox">
    </span>
    <span class="card-content">
      <span class="card-label">GUIDES</span>
      <span class="card-title">Setup Guide</span>
    </span>
  </a>
  <a class="quick-link-card" href="release-notes/">
    <span class="card-icon">
      <img src="images/icon-whats-new.svg" alt="" class="skip-lightbox">
    </span>
    <span class="card-content">
      <span class="card-label">RELEASE NOTES</span>
      <span class="card-title">What's New</span>
    </span>
  </a>
</div>

## Comprehensive reporting for Microsoft Intune

BI for Intune is a Power BI template app that connects directly to your Intune environment via the Microsoft Graph API. No agents on endpoints, no vendor portal — your data stays in your Power BI workspace, governed by your Microsoft 365 tenant policies.

Pre-built dashboards cover device health, compliance, discovered applications, Windows Update for Business, and custom inventory collection. Drill through from fleet-level summaries to individual devices, track OS versions, hardware models, encryption status, and Autopilot enrollment — all with automatic refresh on your schedule.

Extend your reporting with PowerShell-based inventory scripts for BitLocker, local admins, monitors, USB devices, and more. Optional Log Analytics integration provides extended data retention and advanced querying capabilities.

---

## Getting Started

- [Install BI for Intune](guides/install-bi-for-intune.md)
- [Request a Trial License](guides/request-a-trial-license.md)

## Setup Guide

- [Create App Registration](guides/create-azure-ad-app-registration.md)
- [Configure the Dataset](guides/configure-the-dataset.md)
- [Configure Data Sync](guides/configure-data-sync.md)
- [Export API Parameter](guides/export-api-parameter.md)

## Log Analytics Setup

- [Connect Power BI to Log Analytics](guides/edit-azure-ad-app-registration.md)
- [Dataset Settings for Log Analytics](guides/dataset-settings-for-custom-inventory.md)

## Custom Inventory

- [Create Inventory App Registration](guides/create-inventory-app-registration.md)
- [Deploy Custom Inventory Resources](guides/configure-log-analytics.md)
- [Windows Inventory Collection Script](guides/windows-inventory-collection-script.md)
- [macOS Inventory Collection Script](guides/macos-inventory-collection-script.md)

## WUfB Reports

- [Windows Update for Business Reports](guides/wufb-reports.md)

## Administration

- [Dataset Parameters](guides/dataset-parameters.md)
- [Backup Custom Reports](guides/backup-custom-reports.md)
- [Perform In-place Upgrade](guides/perform-in-place-upgrade.md)

## Release Notes

See what's new in each version of BI for Intune.

- [All Release Notes](release-notes/index.md)
