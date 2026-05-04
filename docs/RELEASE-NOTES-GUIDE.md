# PowerStacks Release Notes Guide

This document defines the official release note generation standards for PowerStacks products.

Claude and contributors must follow these rules when generating release notes for:

- BI for Intune
- BI for Defender
- BI for SCCM

These standards ensure consistency across all product documentation and marketing communications.

---

# Release Note Structure

Release notes must always use the following headings **in this exact order**:

1. Product Enhancements
2. New Features
3. Semantic Model Changes
4. Bug Fixes
5. Important Notes

If a section has no content, **omit the section entirely**.

Do not write "N/A".

---

# Terminology Rules

Use the following terminology consistently:

| Incorrect | Correct |
|----------|---------|
| Table | Object |
| Column | Field |

When referencing a specific object or field:

- **Bold object names**
- **Bold field names**
- **Bold page names**
- **Bold parameter names**

Example:

Added new fields to the **DeviceInventory** object: **SerialNumber**, **WarrantyStatus**, **PurchaseDate**.

Do not use quotation marks around object or field names.

---

# Implementation Detail Filter

Release notes should describe **customer-visible behavior only**.

Do NOT include internal implementation details such as:

- API endpoint changes
- query refactoring
- code-level optimizations
- infrastructure updates

Only describe the **customer impact or visible improvement**.

---

# Classification Rules

## Product Enhancements

Improvements to existing functionality.

Example:

• Improved performance of device inventory synchronization for large tenants.

---

## New Features

Brand-new capabilities.

Examples:

• Added new dashboard page **Application Deployment Trends**.

• Added support for Microsoft Graph permission **CloudApp-Discovery.Read.All**.

---

## Semantic Model Changes

Changes to the Power BI semantic model including:

- object additions
- field additions
- field removals
- field renames
- parameter additions

Examples:

Added new fields to the **DeviceInventory** object: **WarrantyStartDate**, **WarrantyEndDate**.

Added new parameter **DeviceHistoryDays** to the semantic model (Default: 30). This parameter controls how many days of historical device data are retained.

---

## Bug Fixes

Use specific wording:

- **Resolved** for customer-impacting issues
- **Fixed** for deterministic defects

Examples:

• Resolved an issue where the **WindowsUpdateStatus** object could return duplicate records.

• Fixed an issue that caused the **ComplianceStatus** field to display incorrect values.

---

## Important Notes

Use this section for:

- breaking changes
- required customer action
- permission changes
- upgrade considerations

Example:

• [Action Required] This version requires an additional Microsoft Graph permission to be added to the app registration. Without this permission, synchronization will fail. Please add **CloudApp-Discovery.Read.All** to your Microsoft Entra ID app registration.

---

# Standard Formatting Rules

Release notes must follow these formatting rules:

- Sentence case
- Period at the end of sentences
- One issue per bullet
- Professional tone
- No internal engineering jargon

---

# Field Addition Format

Single field:

Added **FieldName** to the **ObjectName** object.

Multiple fields:

Added new fields to the **ObjectName** object: **FieldOne**, **FieldTwo**, **FieldThree**.

---

# Field Rename Format (Breaking Change)

Semantic Model Changes:

Renamed **OldFieldName** to **NewFieldName** on the **ObjectName** object. See Important Notes.

Important Notes:

Renamed **OldFieldName** to **NewFieldName** on the **ObjectName** object. This is a breaking change.

---

# Page Update Format

Added new fields to the **PageName** page: **FieldOne**, **FieldTwo**, and **FieldThree** to improve visibility into deployment status.

---

# Parameter Addition Format

Added new parameter **ParameterName** to the semantic model (Default: X).

This parameter controls [brief explanation].

Increasing this value may impact synchronization performance.

---

# Release Note Header

Every release note must begin with:

Release Date: Month Day, Year  
AppSource Version: ####

---

# ActiveCampaign Email Summary (Required)

Each release must include a short email-ready summary.

Structure:

Paragraph 1 — What’s new  
Paragraph 2 — Why it matters (security/compliance focus)  
Paragraph 3 — Who benefits or performance impact

Avoid deep technical implementation details.

Example structure:

This release introduces several enhancements to improve visibility into endpoint compliance and application deployment activity.

These improvements strengthen security reporting by giving IT teams faster access to device inventory data and more reliable synchronization with Microsoft Intune.

Organizations managing large device fleets will benefit from improved performance and more detailed dashboards for monitoring endpoint compliance.

---

# Handling Incomplete Developer Notes

If developer notes are unclear or incomplete:

Insert a clearly labeled note:

[Clarification Required]

Do not fabricate details.

---

# Final Guidance for Claude

When generating release notes:

- Follow the official structure.
- Filter internal implementation details.
- Use Object / Field terminology.
- Surface breaking changes under Important Notes.
- Include the ActiveCampaign email summary.