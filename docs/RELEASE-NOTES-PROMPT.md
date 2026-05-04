# Release Notes Generation Prompt

Use this prompt when generating release notes for PowerStacks products.

This repository follows the standards defined in:

docs/RELEASE-NOTES-GUIDE.md

Claude must follow those rules when generating release notes.

---

# Instructions for Claude

You are generating release notes for a PowerStacks product.

Follow the official release note standards defined in:

docs/RELEASE-NOTES-GUIDE.md

Requirements:

• Use the five official release note sections.  
• Omit sections with no content.  
• Use Object and Field terminology.  
• Filter out internal implementation details.  
• Surface breaking changes under Important Notes.  
• Use the correct Bug Fix classification (Resolved vs Fixed).  
• Include an ActiveCampaign email summary at the end.

---

# Release Information

Product:  
Release Date:  
AppSource Version:  

---

# Raw Developer Notes

Paste the raw developer notes below.

Do NOT modify them before analysis.

```
[PASTE DEVELOPER NOTES HERE]
```

---

# Expected Output

Generate:

1. Fully formatted release notes following PowerStacks standards.
2. Correct classification under the five official sections.
3. Implementation details filtered out.
4. Breaking changes surfaced under Important Notes.
5. ActiveCampaign-ready email summary.

Do not fabricate missing details.

If developer notes are unclear, insert:

[Clarification Required]

---

# Example Workflow

1. Developer sends raw change list.
2. Paste change list into this prompt.
3. Claude generates release notes.
4. Review for clarification markers.
5. Export final notes to Word using the standard template.

---

# Example Developer Notes

```
Added new fields WarrantyStartDate and WarrantyEndDate to DeviceInventory table.
Improved performance of device sync for tenants over 100k devices.
Fixed issue where Windows Update dashboard sometimes showed duplicate records.
Added new parameter DeviceHistoryDays default 30 controlling retention window.
```

---

# Example Output

Release Date: Month Day, Year  
AppSource Version: ####

Product Enhancements

• Improved performance of device synchronization for large tenants.

Semantic Model Changes

• Added new fields to the **DeviceInventory** object: **WarrantyStartDate**, **WarrantyEndDate**.

• Added new parameter **DeviceHistoryDays** to the semantic model (Default: 30). This parameter controls how many days of historical device data are retained.

Bug Fixes

• Resolved an issue where the **WindowsUpdateStatus** object could return duplicate records.

---

ActiveCampaign Email Summary

This release introduces several improvements designed to enhance reporting visibility and platform performance.

The update improves device synchronization performance for large tenants and introduces additional warranty tracking fields to the DeviceInventory object, giving IT teams deeper insight into hardware lifecycle management.

Organizations managing large device fleets will benefit from improved reliability and more complete asset data for reporting and compliance analysis.