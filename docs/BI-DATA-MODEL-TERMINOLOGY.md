# PowerStacks BI Data Model Terminology

This document defines the terminology used when describing the PowerStacks BI semantic models.

Claude must follow these terminology rules when generating:

- release notes
- documentation
- blog content
- technical explanations

These rules ensure consistency across all PowerStacks BI products.

---

# Semantic Model Terminology

PowerStacks BI products use **Power BI semantic models**, not traditional database terminology.

Preferred terminology:

| Database Term | PowerStacks Term |
|---------------|------------------|
| Table | Object |
| Column | Field |
| Database | Semantic model |
| Query | Data source query |

Claude must use the PowerStacks terminology.

---

# Correct Usage Examples

Correct:

> Added **SerialNumber** to the **DeviceInventory** object.

Correct:

> Added new fields to the **WindowsUpdateStatus** object: **UpdateTitle**, **KBNumber**, **InstallState**.

Incorrect:

> Added column SerialNumber to the DeviceInventory table.

Incorrect:

> Added columns UpdateTitle and KBNumber to the WindowsUpdateStatus table.

---

# Object Naming

Objects represent logical entities within the Power BI semantic model.

Examples:

• **DeviceInventory**  
• **WindowsUpdateStatus**  
• **ApplicationInstallations**  
• **DefenderThreatEvents**  

Object names should always be written in **bold** when referenced in documentation or release notes.

Example:

> Added new fields to the **DeviceInventory** object.

---

# Field Naming

Fields represent attributes within an object.

Examples:

• **SerialNumber**  
• **Manufacturer**  
• **OSVersion**  
• **ComplianceState**  

Fields should always be written in **bold**.

Example:

> Added **ComplianceState** to the **DeviceInventory** object.

---

# Page Naming

Power BI report pages should be treated as user-facing features.

Page names should be written in **bold**.

Example:

> Added new visualizations to the **Windows Update Compliance** page.

---

# Parameter Terminology

Parameters control how the semantic model behaves.

Examples:

• **DeviceHistoryDays**  
• **UpdateHistoryDays**  
• **DefenderDataRetentionDays**

Parameters should always be written in **bold**.

Example:

> Added new parameter **DeviceHistoryDays** to the semantic model (Default: 30).

---

# Parameter Explanation Format

Parameters should include a short explanation of their purpose.

Example:

> Added new parameter **DeviceHistoryDays** to the semantic model (Default: 30).  
> This parameter controls how many days of historical device data are retained.

---

# Field Addition Format

Single field:

> Added **FieldName** to the **ObjectName** object.

Multiple fields:

> Added new fields to the **ObjectName** object: **FieldOne**, **FieldTwo**, **FieldThree**.

---

# Field Rename Format

Field rename operations must highlight the breaking change.

Example:

Semantic Model Changes

> Renamed **OldFieldName** to **NewFieldName** on the **ObjectName** object. See Important Notes.

Important Notes

> Renamed **OldFieldName** to **NewFieldName** on the **ObjectName** object. This is a breaking change.

---

# Field Removal Format

Removing a field should always be documented.

Example:

> Removed **DeprecatedFieldName** from the **ObjectName** object.

If the change may impact existing reports, include a note under Important Notes.

---

# Page Update Format

Example:

> Added new fields to the **Device Compliance Overview** page to improve visibility into compliance status trends.

---

# Final Guidance

When describing PowerStacks BI models:

• always use **Object** instead of Table  
• always use **Field** instead of Column  
• always bold object names and field names  

This terminology must remain consistent across:

- BI for Intune
- BI for Defender
- BI for SCCM