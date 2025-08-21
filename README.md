# lab28-iam-identity-center
 Lab 28: Securing AWS Landing Zone Access with IAM Identity Center, Permission Sets, and MFA.
Lab 28: Securing AWS Landing Zone Access with IAM Identity Center (SSO) & MFA
📌 Overview

This lab demonstrates how to configure AWS IAM Identity Center (SSO) in a secured AWS Landing Zone environment. 
The goal is to replace root/long-term IAM access with centralized identity and permission sets across AWS Organizations.

The lab follows a step-by-step, production-like approach, including enabling IAM Identity Center, creating permission sets, 
enforcing MFA, and provisioning secure administrative access.

This documentation includes 80 screenshots for full traceability.

🎯 Objectives
• Enable IAM Identity Center (SSO) in eu-west-1 (Ireland).
• Lock down root user access and enforce MFA for all administrators.
• Create and configure permission sets for secure access management.
• Assign cloud-admin user with Administrator permissions across AWS accounts.
• Test login via AWS Access Portal to validate secure SSO access.
• Provide a blueprint for real-world Landing Zone access control.
🛠 Tools & Services Used
• AWS IAM Identity Center (SSO)
• AWS Organizations (multi-account structure)
• Service Control Policies (SCPs)
• Permission Sets (Administrator, PowerUser, ReadOnly)
• MFA with Authenticator App
• AWS Access Portal
🔐 Implementation Steps
Step 1 — Enable IAM Identity Center
• Navigated to IAM Identity Center → Settings.
• Selected Ireland (eu-west-1) as the home region.
• Enabled IAM Identity Center with AWS Organizations integration.
Step 2 — Configure Authentication & MFA
• Required multi-factor authentication (MFA) for all users.
• Selected Authenticator App as the MFA method.
• Configured session duration = 8 hours.
Step 3 — Create Cloud Admin User
• Created user: Username: cloud-admin, Email: imegcu55@gmail.com, Name: Ime Ben.
• Chose 'Send email for password setup' option.
Step 4 — Assign Groups (Optional)
• Skipped predefined AWS groups.
• Proceeded with custom permission sets.
Step 5 — Create Permission Sets
• Created new permission set: AdministratorAccess.
• Policy: AWS managed AdministratorAccess.
• Session Duration: 1 hour.
• Other sets: PowerUserAccess, ReadOnlyAccess.
Step 6 — Assign Permissions to Cloud-Admin
• Selected management account (285305988025).
• Assigned cloud-admin user with AdministratorAccess.
Step 7 — Accept Invitation & First Login
• Email invitation received → Accept Invitation.
• Redirected to AWS Access Portal.
• Completed password setup.
• Registered MFA device using Authenticator App.
Step 8 — Validate Access
• Logged in via AWS Access Portal: https://d-9367a8c3c1.awsapps.com/start/
• Verified AdministratorAccess across accounts.
• Ensured MFA is required at login.
✅ Outcomes
• Root user access eliminated for daily use.
• SSO enabled with MFA enforcement.
• Cloud-Admin user created for secure centralized access.
• Permission sets provisioned for RBAC (Role-Based Access Control).
• Audit-ready Landing Zone security model achieved.
📊 Lessons Learned
• Region Restriction Enforcement → SCPs required choosing eu-west-1.
• User Experience → Email invitation streamlined onboarding.
• Security Posture → MFA drastically improved login security.
• Scalability → Multiple permission sets allow separation of duties.
⚠️ Limitations
• No external IdP integration (Okta, Azure AD).
• Session duration limited to 12 hours.
• Sandbox setup, not production.
🚀 Significance in Real-World Use
• Replaces insecure root user and long-term IAM credentials.
• Enforces least privilege and centralized identity.
• Demonstrates compliance with CIS Benchmarks & NCSC principles.
• Provides a scalable enterprise multi-account access model.
👤 Author
Dr. Ime Ben
AWS Cloud Security Engineer | DevSecOps | IAM & Identity Governance


AWS IAM Identity Center Lab – Step-by-Step Breakdown
Breakdown of Steps with Screenshots
This section provides a detailed breakdown of the 80 screenshots captured during the execution of the lab. Each screenshot maps directly to a phase of the lab, ensuring full traceability and transparency of the process.
1. IAM Identity Center Setup (Screenshots 1–15)
- Created IAM Identity Center user (`cloud-admin`).
- Configured email invitation for activation.
- User details such as username, email, and role recorded.
- Verified the addition of the new user in IAM Identity Center.
2. Creating Permission Sets (Screenshots 16–30)
- Created `AdministratorAccess` permission set.
- Defined session duration and description.
- Attached AWS managed policies for admin rights.
- Verified provisioning status of the permission set.
3. Assigning Users to Accounts (Screenshots 31–50)
- Assigned `cloud-admin` to the management account.
- Selected `AdministratorAccess` as the permission set.
- Verified account association under organizational structure.
- Reprovisioned permissions to apply updated settings.
4. MFA Setup and Registration (Screenshots 51–70)
- Enabled MFA requirement for secure sign-in.
- Chose Authenticator App for MFA registration.
- Scanned QR code and linked Authenticator App.
- Verified successful MFA registration for `cloud-admin`.
5. AWS Access Portal Login (Screenshots 71–80)
- Accessed AWS login portal via invitation URL.
- Logged in with `cloud-admin` and MFA verification.
- Verified account listed under AWS access portal.
- Completed successful authentication and lab verification.

