---
title: Global Catalog and Access Control
description: 
published: true
date: 2021-06-13T12:28:57.648Z
tags: 
editor: markdown
dateCreated: 2021-06-13T12:28:52.903Z
---

## Global Catalog
- Catalog service provided by AD
- Cross-Domain lookup
  - Domain controllers contain a full writable replica of all objects within its domain
  - Also contain partial read only replica of all other objects (not in domain)
  - Any time a user uses start/Seach/For People or Find Printers or Expands Universal Groups
- First DC in network is automaticaly global catalog server
- Built and updated using AD replication system
- Attributes that are replicated are called the Partial Attribute Set (PAS)

- Functions
  - Enables user searches (LDAP) for directory information
    - All domains in a forest
      - Or Trust relationships also in other forests
  - Validate object references within a forest
    - When an object contains a reference to an object in another domain
    - DC holding that object contacts GC server for validation

  - User principal name authentication
    - Normally done by DC
    - When authenticating users from another domain the GC server needs to do it
  - Every site requires at least 1 GC server
  - Best practice is to put GC on each DC
### DNS - SRV records
- Created by default on DC installation
- Clients find DC through DNS lookup using SRV records
- Used by other domains to find DCs for the requested services
- Regenerated on restart of the Netlogon service on the DC
- Can be imported from Netlogon DNS file
### AD partitions
- AD database partitions:
  - Schema partition
    - Blueprint of all objects and attributes
    - One partition per forest
      - Schema info replicated to all domain controllers
    - Schema master is the only DC on which the schema can be updated
  - Configuration partition
    - info about forest wide AD structure
      - Which domains
      - Which sites
      - Which DCs
      - Which services
    - One per forest
      - Domain Naming Master
      - Replicated to all DC in forest
  - Domain partition
    - Information per domain about: 
      - Users
      - Groups
      - OUs
    - One per DC
    - Many per forest
    - Stored in the global catalog (PAS)
  - Application partition
    - Can be placed in:
      - A child of a domain partition
      - A child of an application partition
      - A new tree in the forest
  - Global catalog partition
    - Only on DC that is a GC server
    - Replicated to other GC servers in forest
### AD Relationships
- Trust relationship = relationship between 2 dom,ains
  - Allows users in one domain to be recognised in the other domain
    - Authentication
  - Lets users access resources in the other domain
  - Let admins administer user rights for users in the other domain
- One-way trust relationship
  - User in domain A can access resources in domain B
  - User in domain B can not access resources in domain A
- In AD trust relationships are always:
  - Two-Way
  - Transitive : If A and B, and B and C trust each other, A and C trust each other
#### AD trees
- Set of domains with contiguous names
  - granchild.child.parent naming
- Handy when divisions or departments have their own DNS names and servers
- Two way trust realtionship between parent and child
  - admins of parent aren't automatically admins of the child domain
  - Policies set in parent domain are not automatically applied in child domain
#### AD forests
- all domains in one forest have two-way transitive trust relationship
- Adding a new domain to a forest, no new config is necessary
  - All users see a single directory through the global catalog
- Multiple forests only needed if they need to be managed seperately
- Trees in a forest are a non-contiguous namespace
- Fores has a single root domain
  -  First domain created
  - Trust relationship between root and all other domains is created automatially
- Two way trust allows a single logon process
  - Authenticate user or computer in any domain on the forest
- Inter-Forest Trusts can be made selectively transitive
  - Which domains and which direction can be set
- To improve performance, one-way transitive trusts enable a shorter path
  - This can be combined into a two way trust
- Transitive trust between all domains in a trree and between all trees in the forest
- Common config information
- Common schema
- Common global catalog
- Types
  - Parent-child trust
  - Tree-root trust
    - Automatically created between a new tree and its root domain
  - Shortcut trust
    - Improve user logon times between two domains which are logically distant by creating a trust between the two domains
  - External trust
    - created between two domains in seperate forests
  - Realm trust
    - Created between windows server and a domain running a non-windows implementation of Kerberos (unix)
#### Flexible Single-Master Operations (FSMO) Roles
- AD is multi-master database
- Changes can be applied on every DC
- Can cause conflicts between DC's
- Define Operations Master roles
   - Forest wide:
      - Schema master
      - Domain Naming Master
   - Domain Wide
      - RID master
        - Assings a pool of RIDs of the global RID pool to other DCs
        - Moving object between domains must happen on this DC
        - When promoting a new DC the RID must be online
      - PDC emulator master
        - Backwards compatibility
        - Time service, Account lockout, process authentication failures
      - Infrastructure master
        - Updating cross-domain object references
        - Tracks changes by comparing with GC
- Only one schema master and one domain naming master per forest
- Updates can only happen on these masters
- A domain of a forest can only have one of the domain wide master roles

## Access control
- Mutual authentication
  - Preferred windows authentication: Kerberos
- NTLM

### Mutual Authantication
- Client must prove identity to server
- Server must prove identity to client
- Can be done through trusted third party (TTP)
  - Kerberos uses a shared secret
  - Using cryptography, Public Key Infrastructure (PKI)
### Kerberos
  - 3-part Authentication
  - Authentication via tickets
  - Password is sent to obtain ticket
  - Steps
    1. Client authenticates to an Authenticartion server
    2. Client receives a time-stamped Ticket-Granting-Ticket (TGT)
    3. Client needs to access a service on another node:
      1. Sends TGT to ticket granting service (TGS)
      2. If TGS accepts TGT, it issues a ticket and a session key
      3. Client uses these to access the requested service
  - Implemented in AD vie Key Distribution Service
    - Domain service on a DC
    - Uses AD as account database and GC for referrals to KDCs in other services
  - KDC is a single process that provides 2 services: 
    - Authentication Service (AS)
    - Ticket-Granting service (TGS)
  - If KDC is unavailable, AD is stopped
  - Security principal name "krbtgt"
    - Account is created automatically
      - Can not be changed
      - Can not be deleted
    - all insttances within a domain use the same account
    - Password is used to encrypt and decrypt TGTs
#### NTLM
- Challenge/response authentication
  - Avoid sending password to server
- Used in case where the preferred authentication can not be used
  - Client authenticates to a server in a different AD
  - Client authenticates to a server that does not belong to a domain
- process:
  1. User sends access request
  2. Server sends a challenge message
  3. Client encrypts challenge with hashed password and sends encrypted response to server
  4. Server sends challenge and response to domain controller
  5. Domain controller compares challenge and response to authenticated user
  6. Server sends response to client

#### Account security
- Can be set using policies
  - Password policies
    - On different levels:
      - Domain level
        - Default domain policy
        - Specific per OU
      - Local level
        - Authenticating locally
      - Specific users or groups
        - Exceptions
  - Authentication policies
  - Account lockout policies

#### Authorization
- Once authenticated,  AD determines which objects user can view or change
  - Access Control Lists (ACLs)
    - List of Access Control Entries (ACEs)
- ACEs apply:
  - On entire object
  - On some properties
##### Inheritance and Delegation
- Inheritance allows admin tasks to be performed at higher levels in the tree
  - Setup inheritable permissions on objects near root
  - Permissions distributed to objects in the tree
- Can be overridden by delegation

- Delegation
  - Grant higher administrative rights to individuals and groups
  - Can be applied to single objects or object containers

- Inheritance
  - Propagate Particular ACEs from a container to all objects within the container
    - Combine with delegation
- Precedence of permission
  - Deny override Allow at the same level or higher parent level
  - Allow override  Deny only if it is on lower parents or the object itself
#### Groups
- Collection of user and computer accounts
- Can be managed as single unit
- Simplify administration
- Delegate administration
  -Assing access rights once
- Email distribution lists

- Group scope
  - Machine local group
  - Domain local
  - global
    - Usable in the domain the group was created in or in any domain that trusts the domain the group is in
  - Universal
    - In domain or in any domain or forest that trusts the domain the group is in

- Group nesting
  - Parent-child relationship
  - Not all combinations are allowed
    - Cannot nest domain local group in global or universal group
      - otherwise local domain group membership would be accessible across the trust

- Best practice
 - Place users in blobal groups
 - Nest them inside domain local groups
  - Used to apply permissions
- Group types
  - Distribution groups
    - Email
    - Not security-enabled
  - Security groups
    - Assing user rights to security group
    - Assing permission to security groups on resources
#### Branch office scenario
- Branch offices are connected via WAN
  - Less reliable
- Replication traffic might be a problem

- Solution: 
  - Read-Only domain Controllers (RODC)
    - DC have a read-only copy of the AD database partitions
      - AD changes on RODC are not replicated back to other DCs
    - Administrator role seperation (ARS)
      - Administration of the RODC can be delegated to a non-administrative user or group
      - Not necessary for high privileged admin to login to DC to perform routine maintenance
    - Password replication policy
      - Determines which users' credentials that a specific RODC caches
      - RODC authentication allow: Users can login without having to authenticate across the WAN
    - Best practice 
      - Global deny list that replicates to DCs
      - Local allow list
  - Univeral Group Membership Caching (UGMC)