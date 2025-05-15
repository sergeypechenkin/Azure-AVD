DRAFT

# Azure-AVD
Azure AVD deployment lab


Steps:

0. Buy a cool custom domain name
0.1 Ensure you are a Global Admin
0.2 Create a cloud-only Hybrid Identity Administrator account for your Microsoft Entra tenant.  assign Hybrid Identity Administrator permissions to this account
2. 
3. Prepare a Domain COntroller
1.1 Deploy an Azure VM with Windows Server 2022 OS
1.2 Promote it to a Domain Controller. Reboot
1.3 Creare Enterprise Administrator account for domain joining AVD host and installing Entra Sync
1.3.1 Create a User Group for AVD users, create users and assign them to a group
1.3.2 Change the UPN suffix to reflect your customm domain name
1.4 Ensure the .NET version 4.8 and greater for the best accessibility compliance.

4. Sync your domain controller with Entra.Cloud Sync vs. Connect Sync???
2.1 Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
2.1 Create the Microsoft Entra Connect Cloud Sync gMSA (group Managed Service Account) to run the agent service (can be created during an express Entra Sync setup)
   Microsoft Entra Connect Sync can be installed on a domain controller, member server, or nondomain joined server.
2.2 To use Microsoft Entra Connect for sync, download the latest version of Microsoft Entra Connect and install it
   https://aka.ms/edx-cld243x-aad. Sign in with a Global administrator account.
   Ensure that Microsoft Entra ID sees the agent: On the Cloud sync | Agents page, verify the agent you installed appears and that its Status is active
   Verify the agent is running on the local server. Search -> Services -> Verify that Microsoft Azure AD Connect Agent Updater and Microsoft Azure AD Connect Provisioning Agent are present, and that their status is Running.
2.3 Configure Microsoft Entra Cloud Sync provisioning. Entra -> Cloud sync | Agents -> Configuration -> "+" New configuration. select the domain you want to sync and whether to enable password hash sync. Select Create.
       https://learn.microsoft.com/en-us/training/modules/implement-synchronization-tools/6-configure-azure-active-directory-connect-cloud-sync Task 4



   Hosts - Entra joined only

   
