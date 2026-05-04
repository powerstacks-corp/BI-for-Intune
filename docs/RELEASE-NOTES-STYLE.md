\# App Store for Intune Release Note Style Guide



This document defines the writing style for App Store for Intune release notes.



The goal is to maintain \*\*consistency with PowerStacks BI product release notes\*\* while adapting terminology for a web application.



These standards apply to all App Store releases.



\---



\# Core Principles



Release notes must be:



• concise  

• customer-focused  

• technically accurate  

• written in professional tone  



Release notes should describe \*\*what changed and why it matters\*\* to customers.



Avoid internal engineering details.



\---



\# Sentence Style



Follow the same style used in BI product release notes.



Rules:



\- Sentence case

\- One issue per bullet

\- Period at the end of sentences

\- No internal engineering jargon

\- No marketing exaggeration



Example:



Correct:



• Improved reliability of application deployment status synchronization.



Incorrect:



• Massive improvements to deployment performance!!!



\---



\# Terminology



Use terminology consistent with PowerStacks products.



Preferred terms:



| Concept | Term |

|------|------|

| app catalog | Application catalog |

| deployment pipeline | Deployment workflow |

| admin portal | Administrative interface |

| request workflow | Application request workflow |

| approval process | Approval workflow |



Avoid developer-centric terms such as:



\- microservice

\- container orchestration

\- dependency injection

\- API refactor



These are internal details.



\---



\# Product Enhancements



Use this section for improvements to \*\*existing functionality\*\*.



Examples:



• Improved performance of the application catalog search.



• Improved reliability of deployment status synchronization with Microsoft Intune.



• Improved visibility into application request history for administrators.



Focus on the \*\*customer-visible improvement\*\*, not the implementation.



\---



\# New Features



Use this section for \*\*new capabilities\*\*.



Examples:



• Added support for automated WinGet package ingestion.



• Added a new \*\*Application Deployment Analytics\*\* dashboard.



• Added role-based access controls for application catalog management.



\---



\# Workflow Changes



Use this section when the \*\*request → approval → deployment pipeline\*\* changes.



Examples:



• Added support for multi-stage approval workflows.



• Added automatic retry logic for failed application deployments.



• Updated the request workflow to allow administrators to approve multiple requests simultaneously.



Workflow changes should clearly explain the operational impact.



\---



\# Bug Fixes



Follow the same standards as BI product release notes.



Terminology:



Resolved — customer-impacting issues  

Fixed — deterministic defects



Examples:



• Resolved an issue where application requests could remain stuck in the Pending state.



• Fixed an issue that caused incorrect application version detection during deployment.



\---



\# Important Notes



Use this section for:



\- breaking changes

\- required administrator action

\- new permissions

\- upgrade considerations



Examples:



• \[Action Required] This version requires an additional Microsoft Graph permission. Please add \*\*DeviceManagementApps.ReadWrite.All\*\* to the Microsoft Entra ID app registration.



• Updated the application deployment service endpoint. Existing deployments will continue to function normally.



Breaking changes must always appear in this section.



\---



\# Implementation Detail Filter



Release notes should not include internal implementation details such as:



\- API endpoint refactoring

\- database schema refactoring

\- container deployment changes

\- infrastructure migrations



Describe only the \*\*customer-visible behavior change\*\*.



Example:



Instead of:



"Refactored the deployment service to use asynchronous Graph calls."



Write:



"Improved reliability of application deployment synchronization."



\---



\# UI Change Guidelines



When describing UI changes:



• Reference the \*\*page or feature name\*\*

• Describe the \*\*customer benefit\*\*



Example:



• Added new filtering options to the \*\*Application Catalog\*\* page to simplify searching for available applications.



\---



\# Workflow Change Guidelines



When describing workflow changes:



• Describe the operational impact.



Example:



• Updated the application approval workflow to allow multiple approvers to review a request simultaneously.



\---



\# Version Header Format



Each release must begin with:



Release Date: Month Day, Year  

Version: X.X.X



\---



\# ActiveCampaign Email Summary



Every release must include an email-ready summary.



Structure:



Paragraph 1 — What’s new  

Paragraph 2 — Why it matters  

Paragraph 3 — Who benefits  



Example structure:



This release introduces several enhancements to improve the reliability and visibility of application deployment workflows.



The update improves synchronization with Microsoft Intune and introduces additional controls for managing application requests and approvals.



Organizations using App Store for Intune will benefit from improved deployment reliability and clearer operational visibility into application requests.



\---



\# Final Guidance



App Store release notes should feel \*\*consistent with BI product release notes\*\* while accurately describing a web application platform.



If two descriptions are possible:



Choose the one that is \*\*simpler and clearer for customers\*\*.

