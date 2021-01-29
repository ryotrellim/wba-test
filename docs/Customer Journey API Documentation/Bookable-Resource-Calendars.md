---
tags: [Scheduling Configuration API]
---

# Scheduling Configuration API Documentation

Calendars are updated in two different ways.

1. The calendar is automatically updated by the Scheduling Platform using availability information in the following endpoints: 
- Bookable Resource Availability:  The hours that a bookable resource is avaiable to administer a service. Add Link to /bookableResources/id/availability
- Bookable Service Availability:   The hours that a bookable service is avialable to be adminstered.  Add Link to /bookableService/id/availability
- Location Availability:  The hours that a location is available to have services administered at that location. Add Link to /location

2. The calendar can also be updated under two different scenarios:
- A Team Member can block or modify a calendar directly.  Scenarios where this could be used is if a Team Member takes an unexpected break, or doesn't show up to work.
- The calendar can be updated when a new appointment is created, deleted or modified.

# Assumption 
Automatically creation of calendar would only happen if the resource is associated with service ID (otherwise process won't be able to create calendar slots which are based on service duration). Process will use the availability information of resource and service duration to define calendar/slot information 

# Open Question:

Scenario 1:  Pharmacy Manager wants to block off times for all Pharmacy services.  How would they do this?
Scenario 2:  An employee does not show up to work as planned (sick, quits, etc).   How does the system update their calendar, and, if necessary, re-assign their appointments? 

Sceanrio 3: Location Availability - We need to revist this scenario. (If bookable service is not assign)

# Availability Documentation

Purpose:  This article describes what the availability endpoint does, how to utilize it, and addresses other concerns.

What:  The availability endpoint allows a developer to discover available days and times for bookable resources that are qualified to administer a service desired by the customer.

Why:  Customers want to discover services, and schedule times to receive them.  

How:  This endpoint allows a developer to input customer preferences, including
 - Location where the customer desires to receive a service, expressed in one of two ways:
    1. Locations near the customers location (geocode, zip code, or city/state)
    2. A specific Store Location
- Bookable Service that the customer desires.
- Dates and Times the customer desires to receive the service.

As an output, the Availability API will provide a list of Bookable Resources, and the dates / times they are available.

# Open Questions



