# Scheduling Overview

The Appointment Booking Platform is comprised of a configuration API, and a consumption API.  

Developers utilizing the Configuration API interact with, and establish relationships among 4 endpoints, including:
<br>
**Locations**:  The Location API provides a list of store locations.  A location is described by, among other attributes, it's address, the company that manages the location, and it's store hours.  
<br>
**Bookable Services**:  The bookable services API can be used to manage or view services for which appointments can be booked at specific locations.  It's is described by, amoung other attributes, it's name, duration, and a short description. A bookable service belongs to many locations.  
<br>
**Bookable Resources**:  The bookable services API can be used to manage or view resources that are eligible to administer specific bookable services.  A bookable resource belongs to many bookable services.

When you create a bookable resource, and bookable resource calendar is automatically created.  
<br>
**Bookable Resource Calendars**:  This API describes the hours of availability of a bookable resource.  It will also show the hours that the location is available or not available.

<br>
<br>
Developers utilizing the User Journey API can construct user journeys by utilizing 6 API endpoints, including all of the aforementioned APIs that are part of the Configuration API, and 2 additional APIs: 
<br>
**Appointment**:  This API is used to manage appointments at a specific location, for a specific service, administered by a bookable resource, for a specific customer.  

When you 

# Getting-Starting-Guide

The beginning of an awesome article...

# Open Question:(Bookable Resource)
1- "When you add the availability of that bookable resource, then his calendar will be updated accordingly", based on the assumption, the scheduling engine will only create a corresponding calendar when there is serviceID associated with resource.

2- Are we planning to use resource Name (specific to walgreen's) in any use case? 

3- Are there any use case where we are using service category?

Scenario 1-  Resource is added wihtout availablity and bookable service information - Correspond calendar won't get created- confirm?

Scenario 2- Resource is added and assign bookable service (no availability hours) - Should it create corresponding calendar automatically and define service slots in calendar based on service duration (define in bookable Service)?

Scenario 3- Resource is added and availablity hours are added (no bookable service assign) -Correspond calendar won't get created- confirm?

Scenario 4 - Resource is added and multiple bookable services are assign - Which service ID should it consider in creating calendar?
