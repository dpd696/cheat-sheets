# Azure Virtual Desktop
Azure Virtual Desktop, Set up Azure Virtual Desktop (formerly Windows Virtual Desktop) in minutes to enable secure remote work. Provide the familiarity and compatibility of Windows 11 with the new scalable multi-session experience for your end users and save costs by using existing eligible Windows licenses. Manage your end-to-end Azure Virtual Desktop deployment alongside other Azure services within the Azure portal.

Project Homepage: [AVD Homepage](https://azure.microsoft.com/en-us/products/virtual-desktop)
Basic Setup Video: [Azure Virtual Desktop (AVD) Setup](https://www.youtube.com/watch?v=jMAanEp-ugI&t=1s)

---
## Creating a Azure Virtual Desktop

Prerequisites:
Azure Tenant with Subscription
Global Administrator

Basic Setup Video: [Azure Virtual Desktop (AVD) Setup](https://www.youtube.com/watch?v=jMAanEp-ugI&t=1s)

---
## Creating a Resource Group

Resource Group is a Container
1.Click on the left menu
2.Go to Resource Group
3.Create a Resource Group
4.Name it something short but relevent ex. AVD
5.Select Region
6.Select Tag (Optional) 
7.Create

---
## Creating a Virtual Network

Virtual network where the Virtual Desktops reside
1.Click on the left menu
2.Go to Virtual Network
3.Select Resource Group
4.Give it a Name ex. AVD-VNET
5.Select Range of IP Addresses or leave Default
6.Modify Securities or leave Default
7.Select Tag (Optional) 
8.Create

---
## Creating a Host Pool

Pool for a group of Virtual Desktops
1.Search at the top for Azure Virtual Desktop
2.Select Host Pools
3.Create
4.Select Subscription
5.Select Resource Group
6.Give it a Name ex. POOL1
7.Select Region (Keep Resources and AVD in same region)
8.Select Pool type
    Personal - Dedicated Virtual Desktop
    Pooled - Floating Desktop
9.If you select Pooled you have to define Load Balancing Algorithm
    Breadth-first - Assign a user per machine per connection
    Depth-first - Set number of users before another machine is created
10.Set Maximum Session Limit
11.Click Next:Virtual Machine (This will be done on another step)
12.Click Next:Workspace (This will be done on another step)
13.Click Next:Advanced (Optional to enable Diagnostics)
14.Click Next:Tags (Optional)
15.Click Next:Review and Create

---
## Creating a Virtual Desktop

Virtual Desktops
1.Search at the top for Azure Virtual Desktop
2.Select Host Pools
3.Select your Pool
4.Select Session Host
5.Click Add
6.Click Next:Virtual Machine
7.Give it a Name Prefix ex. WDE
8.Select Region
9.Set Availability (None Required)
10.Select Image
11.Set Virtual Machine Size (Default)
12.Number of VM's
13.OS Disk Type (Default)
14.Boot Diagnostics (Default)
15.Select Network
16.Public Inbound Ports  (No for client Unless using RDP)
17.Join to Domain (Option to selct Azure Active Directory)
18.Enroll in Intune  (Default)
19.Create Local Administrator Username and Password
20.Click Next:Advanced (Optional to enable Diagnostics)
21.Click Next:Tags (Optional)
22.Click Next:Review and Create

---
## Assigning a Virtual Desktop

Virtual Desktops Assignments
1.Search at the top for Azure Virtual Desktop
2.Select Host Pools
3.Select your Pool
4.Select Application groups
5.Select the group that was created
6.Select Assignments
7.Click Add
This gives access to the pool and now we need to give access to the machines
8.Click on the left menu
9.Go to Resource Group
10.Select Resource Group
11.Select Access Control (IAM)
12.Click Add and Select Add Role Assignment
13.Search for "Virtual Machine User"
14.Select "virtual machine user login"
15.Select Members
16.Review and Assign

---
## Creating a Workspace

Workspaces are what shows up on the Client (VDI or APPS)
1.Search at the top for Azure Virtual Desktop
2.Select Workspaces
3.Create
4.Select Resource Group
5.Give it a Name ex. Workspace
6.Give it a Friendly Name ex. WS
7.Click Next:Application groups (Here you can assign individual applications)
8.Click Next:Advanced (Optional to enable Diagnostics)
9.Click Next:Tags (Optional)
10.Click Next:Review and Create

---
## Worspace Assigning Application Groups

Access to Workspace
1.Search at the top for Azure Virtual Desktop
2.Select Workspace
3.Select your Workspace
4.Select Application groups
5.Click Add
6.Slect your Application Group and click +

---
## Accessing from Web Browser

Access Desktop from Web Browser
1.Search at the top for Azure Virtual Desktop
2.Select Host Pools
3.Select your Pool
4.Select RDP Properties
5.Select Advanced
6.Add to the end ";targetisaadjoined:i:1"