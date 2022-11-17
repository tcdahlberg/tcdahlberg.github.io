---
title: Creating an Event Host
parent: Standard Features
---


# Create an Event Host
You can create an event host for a specific event instance and it can be applied to appointments on an event registration record.

1.	To create an event host from an event instance, hover the cursor to the “Summit Event Hosts” on the Summit Event Instance page. A lookup list of all related event hosts will show up. Click the New Summit Event Host to create a new event host.  
 
2.	Then you will need to choose an event host record type and click Continue.
The record type has the following picklist values:
* Class: Visit a class
* Coach: Visit with a coach
* Counselor: Admission Counselor Visit
* Faculty: Visit with a faculty member
* Housing: A housing host (dorm room overnight)

_Note: Housing is the most common use of the record type._
 
_Note: Since the event host is created from an event instance, the event instance’s identification number(Event Instance field of the Summit Event Instance object) is automatically filled into the field of Summit Event Instance in the event host edit page. If you do not create an event host from an event instance, but by going to the Summit Event Hosts object and clicking New, you will need to manually put in the event instance number that matches an existing event instance record. We recommend creating an event host from an event instance._

3.	You will need to enter information to the fields in the Summit Event Host Detail section. The fields are shown and described below.

## Summit Event Host Detail (Information)
**Summit Event Host Name**: An identification number of each event host. It is a standard Salesforce field and displays in a format of HOST-{0000}. The system will automatically generate and assign a number to this field once an event host is created. No need for any user input and this field cannot be edited.

**Summit Event Instance**: The event instance that the event host belongs to. It is a lookup field that relates to the Summit Event Instance object. As mentioned above, the value must be matched with a record in the Summit Event Instance object. When you hover the cursor over to the Summit Event Instance field on the View page, a mini page of the event instance will show up.
 
_Note: The Summit Event Instance object and Summit Event Host object have a Master-Detail relationship and the Summit Event Instance is the master object. An event host must belong to one event instance. If an event instance is deleted, all related event hosts will be deleted too. Although the event host belongs to an event instance, the event host is directly related to a specific appointment in a registration for a certain event instance. For more details, please refer to “How to assign an event host?” below._

**Record Type**: The event host record type that you choose in Step 2 above. You can still modify the event host record type after Step 2.

**Last Name**: Last name of the host (if any). 

**First Name**: First name of the host (if any).

_Note: For overnight hosting, the last and first name is usually the name of the responsible person such as an admission officer/student ambassador._

**Preferred Title**: The preferred title of the host (Professor, Dr., Burgermeister Meisterburger).

**Gender**: The gender of the host. It is very important for overnight hosting. 

**Undergrad Major**: The undergraduate major that the host is pursuing. 

**Department**: The department where the host is working.

**Contact**: The contact record in the Salesforce for the host. The value in this field must be matched with a contact record in the system. You can manually enter a value or use the lookup form by clicking the lookup button on the right. 

**Time**: The time of the hosing. The data type of this field is Time.

**Formatted Time**: The value of the Time field that is in “12-hour AM/PM” format. The data type of this field is Formula(Text).

**Course Name**: If the event host record type is Class, then this field should have the value of the name of the hosting course. 
 
**Building**: The name of the building where the hosting will be happening. You can select a St. Thomas building from a dropdown list.

**Location**: Room and building number, address, where hosting will be happening.

**Additional Comments**: Additional comments about the host that will appear in any generated itinerary. 

**Max Available**: The number of registrants this host can accommodate.

**Assigned**: The number of registrants currently assigned to this host. For more details, please refer to “How to assign an event host?” below.

**Remaining**: The remaining amount of spaces left in the max capacity of registrants a host can take. Remaining=Max Available-Assigned. 

4.	Click Save or Save & New to save the record

_Note: How to assign an event host?_

_Please note the end-user/registrant does not have any permission to assign an event host. So you won’t see any impacts from the event host on the event registration page that the end users/registrants can view. The event host is assigned from the admin side(salesforce users). An event host can only be assigned to a specific appointment of a registration for an event instance. Before assigning an event host to a registered appointment, please make sure you have set up an event host for the event instance, a registrant has registered for that event instance and the registration includes an appointment._

Step 1: 
Go to the Summit Event Appointments in a registration. Click the Summit Event Appointments button at the top to go to the list at the bottom of the registration page. Or you can hover the cursor to the Summit Event Appointments button to open up a lookup list. Choose an appointment in the list by clicking the value/hyperlink of the Event Appointments Name field. You will be directed to the Summit Event Appointment page.
 
Step 2: 
When you are in the Summit  Event Appointment page, click the Assign/Unassign Host button. 
 
A window will pop up and let you choose a Host Type.
 
Step 3:
Select the Host type that you have set up for the event host record of the event host of the event instance that the registration and appointment belong to. If the value of the Remaining field of the event host is larger than 0, the Host List should show records of the available hostings for you to choose. Choose a hosting and click the Assign… button to assign the event host to the appointment. 

_Note: If the value of the Remaining field is 0 or below, there will be no records showed up under the Host List._
 
Step 4:
Once you click the Assign… button, the window will exit and you can find that the fields of Host Name, Host Location, and Event Host in the Summit Event Appointments page are automatically filled in with the event hosting info. That means you have successfully assigned an event host to the appointment. The number in the Assigned field and Remaining field of the event host will be updated accordingly as well. 

If the Appointment Status is changed to Confirmed, you will find the hosting information in the Generated Itineraries section on the event registration page.

_Note: When the Appointment Status is changed to Confirmed, an email of the appointment and hosting information will be sent to the registrant._
 
_Note: Please note that the Location value in the Generated Itineraraies is not the value of the Host Location, it actually pulls the value from the Building field in the related appointment. Since it is the location of the appointment, not of the hosting._
