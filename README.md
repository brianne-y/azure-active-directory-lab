# Azure Active Directory Lab: On-Premises AD DS in a Cloud-Hosted Environment

## Overview
This lab simulates a corporate Active Directory environment deployed on Windows Server 2022, hosted in Microsoft Azure. The goal was to replicate the user lifecycle management and access control workflows found in a real enterprise IT environment — from initial domain configuration through bulk user provisioning, OU structuring, security group management, and GPO enforcement.

## What Was Built
Domain Controller Deployment:
Provisioned a Windows Server 2022 VM in Azure and promoted it to Domain Controller via the AD DS role installation wizard. Configured the forest and domain from scratch, then validated domain health through Server Manager and dcdiag

Organizational Unit Structure:
Designed an OU hierarchy mirroring a corporate org chart — separating administrative accounts from standard users to enforce policy boundaries and maintain least-privilege access control. OU design directly determines GPO inheritance, so this step was treated as a foundational security decision, not just an organizational preference.

Security Group Configuration:
Created role-based security groups and assigned users according to their access tier. Group membership controls resource permissions rather than assigning access at the individual user level — consistent with RBAC best practices.

Bulk User Provisioning via PowerShell:
Wrote a PowerShell script to automate the creation of multiple user accounts simultaneously, including proper OU placement and group assignments. This reflects real onboarding workflows where manual account creation at scale introduces both inefficiency and human error.

Group Policy Object (GPO) Enforcement:
Created and linked a GPO to enforce an account lockout policy: accounts lock after 3 failed login attempts. This was applied at the domain level and validated against test accounts to confirm inheritance and enforcement.

---

## Key Concepts Applied

Least Privilege Access Control: Users were provisioned with only the permissions required for their role. Admin-tier accounts were kept in a separate OU from standard users.

RBAC via Security Groups: Access is assigned to groups, not individuals. This simplifies both provisioning and deprovisioning, and keeps access auditable.

GPO as a Security Baseline Tool: Group Policy was used to enforce account lockout thresholds across the domain, demonstrating how policy can be used to harden an environment without touching individual machines.

Automation for Consistency: Bulk provisioning via PowerShell reduces the risk of misconfigured accounts during onboarding and mirrors how IT teams manage user creation at scale.

---

## Troubleshooting Encountered
Part of building this environment involved working through real configuration issues — including RDP connectivity problems related to NSG inbound rules, and verifying that GPOs were correctly linked and applying to the intended OUs using gpresult and rsop.msc. These weren't scripted problems with scripted answers — they required reading logs, checking configurations, and iterating until the environment behaved as expected.

---

## Conclusion: Why This Lab Matters for Help Desk
The majority of help desk tickets in an AD-managed environment touch this infrastructure directly — account lockouts, password resets, group membership issues, access requests, and onboarding. Understanding how the backend is configured makes it significantly easier to diagnose and resolve those tickets accurately and efficiently, rather than following a script without understanding the underlying system.

This lab has prepared me to walk into a professional environment and confidently assist users with their most common (and most critical) technical needs.
