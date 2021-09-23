---
title: Active Directory Part 1-3
description: Start Active directory - LDAP (included)
published: true
date: 2021-06-12T19:55:09.458Z
tags: 
editor: markdown
dateCreated: 2021-06-12T17:35:07.120Z
---

## Active Directory
- Why use Active Directory?
  - Centralized managment of: 
    - Users , resources, security policy
  - Single Sign-On
- Without Acitive directory
  - Users and security defined one each client and server
    - High maintenance
    - Hard to change
    - No overview
    - Remote/centralized managment?
### AD data
- Centralized data repository
  - Ntdis.dat file
  - Objects
    - Users, computers, apps, resources,...
### AD architecture
#### Domain
- Manage access to a set of network resources
  - Apps, printers,...
  - For a group of users
- User logged in to domain instead of a local host
  - Access to domain resources
    - On any number of servers in the network
- WIN NT
  - All data stored in domain database
  - Domain controller to control the database
    - Windows server promoted to role of domain controller
    - Primary and backup domain controller
    - PDC replicate database to BDC periodically
- WIN NT Replaced By Active Directory
  - Multi-master replication
  - All domain controllers are peers
  - Domains no longer the only way to divide administrative priviliges
    - OUs
    - No more limit on users


- Security Boundary
  - Security rules in the domain apply to objects in the domain
  - Each part of an organization can have their own security rules
- Administrative Boundary
  - All objects can be managed within the domain
  - Large organizations can be split into multiple domains

#### Domain controller
- AD is managed on a server called a Domain Controller
- More than one DC can exist
  - Multi-Master replication
#### Global catalog
- AD is base on a database, the global catalog
  - User logon
  - Directory queries
- Stored on 1 or more DC's

#### Authentication
- Clients are joined to the domain
- Domain users authenticate to a DC
#### Forests
- Larger organizations can have multiple domains
- Domains are grouped in forests
  - Parent child relationship
    - Domain trees
- Domains in a forest are related
  - Trusts
  - Common [schema](#schema)
- All domains in a forest share the same AD schema
  - Common object definition
  - Schema can be modified
    - Only on one AD
    - Changes are replicated
- All domains in a forest have their own DC
  - Delegated administration
  - Users in domain can authenticate on DC in own domain
    - Can authenticate via other domains using trusts

#### Schema
- Each object has its own structure = schema
  - The fields in a schema are called attributes
- Schema defines what an object should look like, objects follow these rules
ex: User schema
fields: First name, Last name, initials,...

#### Trusts
- Two way trust relationship between all domains withing a forest
  - Users can be authenticated in any domain of the forest
  - Does not mean they get authorized
    - Can get recognized as a domain user but not allowed to access things on that forest
#### Domain functional level
- Each new version of AD has new functionality
- The oldest version of AD in a forest determines functionality
  - This is the domain functional level of a forest
### OU's And Sites
#### OU - Organizational units
- Smaller administrative/security entity within domain
- allows finer control over objects
  - Objects can be inside an OU
  - Security policies can be applied to an OU
  - Moving an object to that OU applies those policies to the object
- Can contain other AD objects
 - users, groups, computers, other OU's
- OU's can be used to delegate privileges
  - Can have their own administrator
- Much more flexible than domains
  - Can be moved and deleted easily
#### Functional vs physical
- Domains and OU' s are functional views of the organization
  - Can contain resources from lots of physical locations
  - one physical location can contain resources from different domains and OU's
  - Contain resources that belong together from an administrtive/security point of view
- Sites represent a physical location
  - Lets AD know where resource is located
  - Authentication and replication
### Replication
- Any change on any DC is replicated to all other DC' s
  - DC's on the same site this is done as soon as possible
- By default this is every 3 hours

### Group policies
- Collection of user and computer configuration settings
- managed centrally
- Can be linked to objects
- Once linked define how: OS, network resources and apps and programs operate for users
#### Benefits
- Maintain and enforce company standards
- Automation
- Locking settings
- Flexibility in settings

#### Usage
- Define and config scripts that run at: 
  - Startup
  - Shutdown
  - logon
  - logoff

- Change registry settings
- Deploy and manage apps
- Password and account policies
- Redirect folders
- Enforce software installation

#### Define
- You can define group policies that affect:
  - A computer
  - A user
#### GPO Hierarchie
- Top level nodes
  - Computer & user config
  - They don' t influence each other
- Second level nodes
  - Software settings
      ex: policy settings for installing, removing and updating software
    - Define how software and apps are installed
    - Can be used to deploy new apps
    - Make a specific app only available to certain users

  - Windows settings
      ex: Policy settings for installing and connecting to windows OS
      - Scripts extension
        - Startup / shutdown
        - Logon / logoff
        - Logoff is processed before shutdown
      - Security settings
        - Computer configuraton:
          - Account (password and account lockout settings)
        - User configuration: 
          - Folder redirection (redirecting user folders to another location)
  - Administrative templates
      ex: Policy settings for the registry
      - Customized registry
        - User config settings go to HKEY_CURRENT_USER(HKCU)
        - Computer config settings go to HKEY_LOCAL_MACHINE(HKLM)
      - App vendors and devs
        - Develop administrative templates with custom settings for product
        - Publish via group policies
      - Subnodes: 
        - Windows components (internet explorer, terminal, Task scheduler ,etc...)
        - System (user profiles, group policies, scripts, etc...)
        - Network (dial-up, offline files, and other group policy specific to computer config)
#### Group policy Objects (GPO)
- AD object
  - Contains one or more GP setting
- Can be linked to: 
  - Computers
  - Sites
  - Domains
  - OUs
- Linking applies GPO recursively to container
#### Group policy hierarchy
- Local group policy
- AD-based group policy
- Inheritance
  - Policy set on one level, all levels below it inherit the policy
  - Policy setting further down take the precedence
  - Can be blocked if setting from higher level is undesirable at lower level
    - No blocking of AD-level towards local policies!!!!!
  - Can be enforced (guarantee that higher level is being applied at lower levels)
#### WMI Filtering
- WMI can be added to limit computer objects this GPO will be applied to
  - Based on attributes such as:
    - OS version
    - CPU architecture
    - Windows server roles
    - Registry settings
    - ...
#### Loopback processing
  - Allow user settings to be applied to a computer as if they are part of the computer settings
  - Modes
    - Replace : Do not consider user policies at all
    - Merge : Consider both, in case of conflict use computer policy
#### GPO Processing Sequence
- Computer config settings processed first
- Startup scripts execute
- User is logged on, profile is loaded
- User config GPO loaded and executed
- Logon scripts executed
- UI displayed according to GPO

#### Multiple local GPOS
- To allow for different local GPOs depending on the local user
- 3 levels: 
  - Local computer policy
  - Administrators and non-administrators local group policy
  - User-specific local group policy
#### Update GPOS
- Update clients
  - GP's are refreshed regularly (default 90 minutes)
  - Can be done manually
#### User profile 
- Created the first time a user logs on to a computer
- At logons the system loads the profile and other components configure the environment according to the info
- Profile contents
  - NTUSER.DAT
  - My documents
  - Favorites, Cookies and History
  - Desktop
  - ...

- Types
  - Local user profile
    - Created first time a user logs on to a computer
    - stored locally
    - Changes made are specific to user and computer
  - Roaming user profile
    - Copy of the local profile that is stored on a server share
    - Downloaded to any computer the user logs on to
  - Mandatory user profile
    - Administrators can use this to specify settings for users
    - Only admins can change
    - Changes made by users to desktop settings will be lost at log off
  - Temporary user profile
    - Issued when an error condition prevents user profile from loading
    - Deleted at end of session

## LDAP
- Lightweight Directory Access Protocol
- Directory service
  - Directory = location of everything in a network
  ex: DNS : domain name vs ip address
  - Allows searching for object without knowing its location
### LDAP hierarchy
- Tree structure
- Root directory
  - Country
    - Organization
      - Organizational unit
        - ...

### LDAP Directory
- Database
- Distributed among different servers
  - Each their own Area of responsibility or Naming Context (NC)
  - Synchronized periodically
- Directory System Agent (DSA)
- If it is queried, it passes on the request to other servers (other NC) if necessary
  - Still responsible for answering the request
- Set of objects
  - Objects with attributes that have names and values
- Each entry has a unique identifier
  - Distinguished Name (DN)
    - Case insensitive
  - Relative Distinguished name (RDN)
### AD schema, objects
 - AD schema defines objects and their attributes
 ex: User object has : FirstName, LastName, Department, Email,...
 - Extensible (attributes can be added)
 - Objects can be queried using LDAP
### Object naming in AD
- An object has several different names
  - Security principal name
    - Automatically assigned an SID for logon and access to resources
    ex: user account, computer, group
    - Within a single domain
  - Security identifier (SID)
    - Unique number created by the Windows server OS
    - Assigned to security principal object
    - Used to identify objects
    - RID is appended to domain SID to uniquely identify object in domain
    - Access control entry (ACE)
      - Objects are protected by one or more ACEs
        - Ace identifies users or groups that can access the object by SID
  - LDAP name
    - All access to objects occurs via LDAP
    - Support querying by: 
      - LDAP DN and RDN name
      - LDAP URLs
      - LDAP-based canonical names
  - Object GUID
    - Global unique identifier
      - SIDs unique withing a domain
        - changes when moving domains
      - GUID unique across all domains
        - never changes
  - Logon names (UPN, SAM)
    - Users require logon name to gain access to a domain
    - Two types:
      - UPN (user principal name)
      ex: user@my-very-own-domain
        - User-friendly name
        - Independent of the DN
      - SAM (Security Account Manager name)
        - Backwards compatibility with Windows NT