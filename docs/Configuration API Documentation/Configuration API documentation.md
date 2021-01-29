---
tags: [Scheduling Configuration API]
---

# Overview

The Scheduling Configuration API allows developers to configure appointment services so that front-end developers can build customer journeys.

There are 3 main resources required to configure Scheduling services
1. **Locations**:  a resource to define where bookable services are offered and administered
2. **Bookable Services**: a resource to define what service or services offered to customers, the duration required to receive the service, and a location where the service is offered.  
3. **Bookable Resources**:  a resource to define resources (e.g., people, rooms, teams, etc) qualified to administer a service.

# Preconfigured Resources

WBA maintains the data for WBA Location and Bookable Resource.  Specifically:
1. **Locations**:  WBA will maintain the master list of store locations where appointments may be offered.  When a location is opened, closed or updated, WBA will update the Locations service database to reflect the change.  When changes occur that can impact scheduling, the Location service will generate a webhook to notify developers of the update.  
2. **Bookable Resources**:  WBA will maintain the database of team members eligible to administer bookable services.  When a team member is hired, departs, or changes their role or location, WBA will update the Bookable Resource service database to reflect the change. Specifically:
-- Newly Hired Member:  A new entry will be made in the Bookable Resources database via the Bookable Resources API
-- Team Member Leaves WBA:   The team member's record in the Bookable Resources DB will be changed from "Active" to "Inactive"
-- Team Member Leaves WBA:   The team member's record in the Bookable Resources DB will be changed from "Active" to "Inactive".   A Team Member record with the updated information will be added to the Bookable Resources resource.

When changes occur that can imppact scheduling, the Bookable Resource service will generate a webhook to notify developers of the update. 

# Configurable Resources

Developers have the ability to configure resources in their organization.  Permissions are enumerated as follows:

## WBA Developers
1.  View WBA locations 
2.  Create, edit, and delete Bookable Services for developer's WBA Organization (e.g., Boots, Walgreens, etc)
3.  View Bookable Resources for developer's WBA Organization
4.  Edit Bookable Resources attribute "Eligible Bookable Resources" for developer's WBA Organization
5.  Create, edit, and delete Custom (i.e., resource not supplied by the Scheduling Platform) Bookable Resources

## Partner Developer
1. View WBA Locations
2. Create Partner locations, bookable services, and bookable resources, and establish relationships amongst them.

# Prerequisites

There a no prerequisites to utilize this service.

# Getting Started

Step 1: Determine the locations that will be utilized to administer services. Options include:
- Walgreens Locations
- Boots Locations (ROADMAP)
- Partner Locations (ROADMAP)
- Other WBA Properties (ROADMAP)

To browse locations, use the GET Locations endpoint as part of the Locations API

Step 2 (Optional)(ROADMAP):  Create a non-WBA Location:  If the location you plan to administer a service isn't available in the Location service, you may add a custom location.  Custom locations are most often utilized to offer services at a Partner or Customer location.  For example, if a corporate customer asks Walgreens pharmacists to administer flu shots at their corporate offices, a new location would be created in the Location service.  

** Note that the Locations service, in part, stores information about WBA locations.  This data is managed by the developers responsible for the Location service, and cannot be updated by developers consuming the service. 

Step 3: Create a Bookable Service using POST Bookable Resources. Required fields include:
- Service Name:  A recognizable name for the service.  
- Location ID:  You must specify which location the service will be offered. If you wish to offer the same service at multiple locations, you must create a service for each location you plan to offer the service.  
(FOR DISCUSSION: Is there an way we can offer a Bookable Service at all locations, so that developers don't have to write a script to create a bookable service for each location?   OnSched has a concept of a "Location HQ", in which a service is assign to headquarters and is therefore available everywhere)

Step 4:  Determine the Bookable Resources that will be utilized to administer services.  Options include:
- Customizable Bookable Resources -- Define bookable resources however you see fit.  For example, you could add a person or a room, or any other resource that is capable of administering a vaccine (Phase 0).
- Walgreens Employees (Phase 1) 
- Boots Employees (Phase 2)
- Other WBA Employees (Phase 3)
Use the POST Bookable Resources Endpoint to create bookable resources

Step 5A:  Assign a Bookable Resource to one or more Bookable Services.  Doing so will automatically create a Bookable Resource Calendars that can used to assign the Bookable Resource to appointments.

Step 5B:  If you plan to add a customizable bookable resource, you may do so




