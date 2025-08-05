🚀 Workstation Manager
Unified Management Tool for HP Anyware Connector & Services
This application simplifies the management of HP Anyware Connectors and related services by consolidating all major operations into a single, user-friendly interface. It removes the need for multiple tools or manual configurations and empowers teams to deploy, monitor, and troubleshoot seamlessly.

🔍 Please test the application thoroughly. If you encounter any issues or have suggestions, your feedback is most welcome and genuinely appreciated.

✅ Key Features and Capabilities
✅ Create and manage deployments using API tokens.

✅ Install, update, or uninstall connectors remotely via secure SSH.

✅ View connector health and run Active Directory diagnostics.

✅ Assign/unassign users and workstations via intuitive UI.

✅ Configure security groups, Federated OAuth, and SSO.

✅ Automate lifecycle events via webhook integration.

✅ Run pod-level diagnostics & LDAP certificate validation.

1. 🔐 Login & API Token
Visit https://cas.teradici.com and sign in.

Navigate to your profile and generate an API Token.

When prompted by the application, paste your token to proceed.

2. 🏗 Deployment Management
Create a new deployment using a registration code.

Selecting a deployment auto-loads related:

🧩 Connectors

👥 Users

🖥 Workstations

3. 🔐 Establish SSH Connection
To manage connectors remotely, configure your Linux host for SSH:

bash
Copy
Edit
# Connect via PEM key (if applicable)
ssh -i yourkey.pem ec2-user@<IP>

# Switch to root and update
sudo su
yum update -y      # or apt update

# Edit sshd_config and ensure:
Port 22
PasswordAuthentication yes
PermitRootLogin yes

# Restart SSH
systemctl restart sshd

# Set root password
passwd

# Reconnect
ssh root@<IP>
4. 🔧 Connector Management
Installed Connectors
View all connectors linked to the selected deployment.

Generate Connector
Enter a name → Generate API token for the connector.

Install Connector Remotely
Fill out the fields:

Domain (e.g., example.local)

Domain Controller FQDN(s)

Service Account Credentials

Computers DN / Users DN
Click Install to deploy remotely over SSH.

Update / Uninstall
Easily update or remove connectors from the interface.

5. 🛠 Troubleshooting & Diagnostics
Check Health – Validate connector status.

Diagnose AD – Verify domain, sync, and authentication.

Check K8s Pods – Ensure all connector containers are active.

LDAP Certificate Check – Validate domain controller cert.

6. 🔐 Security Group Management
Enable or disable SG for connectors.

Public IP is required to activate SG from the app.

7. 🧑‍💻 Workstations & Users
Assign/unassign workstations to users.

Start, Stop, Restart actions (requires Service Account).

Supports real-time filtering & tabular summaries.

8. 🌐 Federated OAuth
Configure using Client ID and IDP URL.

Enable or disable OAuth with one click.

✅ Example: Setup with Okta or Duo

9. 🔑 SSO Configuration
Supports:

Active Directory CA Web Enrollment

Private Key + Certificate

🛠 Setup Guide: Integrate with Okta SSO

10. 🏊 Pool Management
Create and manage pools for grouping users/machines.

Perform assignments, deletions, and updates via UI.

11. 🔁 Webhook Integration
Enable automation:

Triggered on Start, Stop, or Resource Events.

Actions:

✅ Create Webhook

✅ Enable / Disable

✅ Get Webhook Details

Monitor events directly via the integrated output console.

12. 📊 Session History
View historical and active session logs:

Session ID

User

Start / End time

State & machine mapping

🧩 Additional Notes
⚠ SmartScreen Warning on Windows
Because this is a newly built unsigned .exe:

You may see "Windows protected your PC".

To proceed:

Click More Info

Click Run anyway

Rest assured: this app is safe and does not install anything.

📥 Download & Run
Download the .zip package.

Extract and double-click ManagerAPI.exe.

Paste your token when prompted and begin managing!
