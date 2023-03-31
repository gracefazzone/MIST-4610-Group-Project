# Group Project Team 12482_1

The concert management company needs to effectively track all aspects of their operations. The company owns several venues with different names, capacities, locations, and different main points of contact for rental inquiries. The venues grant spaces for multiple vendors of different names, types, and permits to sell items in their respective stalls that range in flat rental charges and sizes. The company also has a designated team of staff members that the company wants to store information about; the company wants to store information about their names, emails, phone numbers, addresses, and pay rates. The concert management team would also like to analyze the shifts of each staff member and retain data about the start and end time. 

Next, the concert management team would also like to save information about agents who manage the performers. The company wants to save the names and phone numbers of the agents and the name of the performers they manage. Design a data model to accurately depict the process of concert management. With each performer, they will fall in a specific genre category. With each concert that will be performed, the company wants to track the name, date, and time of the concert.

Finally, the company wants to track attendee name, contact, and credit card numbers. The attendees purchase different tickets from different platforms, at different costs, and their seat numbers. The concert will feature multiple performers and can take place at multiple venues. Create a data model that represents the entire process of planning the concert, from purchasing tickets and managing logistics to booking performers and managing staff. 
# Team Members
- [@Grace Fazzone](https://github.com/gracefazzone/MIST-4610-Group-Project)
- [@Annie Li](https://github.com/anniewli/annieli)
- [@Young Kim](https://github.com/Youngiyoung/Group-Project)
- [@William McBride](https://github.com/WilliamMcB23/William-McBride-Project-1---MIST-4610)
 - [@Gustav Bringle](https://github.com/gustavbringle/Sky)

# Data Model

![Logo](https://github.com/gracefazzone/MIST-4610-Group-Project/blob/main/dm1.png?raw=true)


## Data Dictionary

```sql

```
Table: Agent
| Column Name | Description               | Data Type | Size | Format | Key |
| ----------- | ------------------------- | :-------- | ---- | ---- | -----
| agentID     | Unique Agent Identifier   | INT       |      |      | PK
| fName       | The agent's first name    | Text      | 45   |      |  |
| lName       | The agent's last name     | Text      | 45   |      |  |
| phone       | The agent's phone number  | Text      | 20   | 999-999-9999 | | 

Table: Attendee
| Column Name | Description                  | Data Type | Size | Format | Key |
| ----------- | -------------------------    | :-------- | ---- | ---- | -----
| attendeeID  | Unique Attendee Identifier   | INT       |      |      | PK
| firstName   | The attendee's first name    | Text      | 45   |      |  |
| lastName    | The attendee's last name     | Text      | 45   |      |  |
| email       | The attendee's email         | Text      | 45   |      | | 
| phone       | The attendee's phone number  | Text      | 20   | 999-999-9999 | |
| creditCardNumber | The attendee's credit card information | Text | 16   | | |

Table: Company
| Column Name | Description               | Data Type | Size | Format | Key |
| ----------- | ------------------------- | :-------- | ---- | ---- | -----
| plannerID   | Unique Planner Identifier | INT       |      |      | PK
| companyName | The name of the company the planner is with | Text | 45 |      |  |

Table: Concert
| Column Name | Description                 | Data Type | Size | Format | Key |
| ----------- | -------------------------   | :-------- | ---- | ---- | -----
| concertID   | Unique Concert Identifier   | INT       |      |      | PK
| concertDate | The date of the concert     | Date      |  10  | YYYY-MM-DD |  |
| concertTime | The concert start time      | Time      |      | HH-MM-SS |  |
| opener      | The opening performer       | Text      |  45  |      | | 
| performerID | Unique Performer Identifier | INT       |      |      | FK |
| venueID     | Unique Venue Identifier     | INT       |      |      | FK |

Table: Genre
| Column Name | Description               | Data Type | Size | Format | Key |
| ----------- | ------------------------- | :-------- | ---- | ---- | -----
| genreID   | Unique Genre Identifier     | INT       |      |      | PK
| genreName | The music genre name        | Text | 45 |      |      |

Table: Performer
| Column Name | Description                 | Data Type | Size | Format | Key |
| ----------- | -------------------------   | :-------- | ---- | ---- | -----
| performerID | Unique Performer Identifier | INT       |      |      | PK
| performerName | The name of the performer | Text      | 45   |      |  |
| agentID     | Unique Agent Identifier     | INT       |      |      | FK |
| genreID     | Unique Genre Identifier     | INT       |      |      | FK | 

Table: Shift
| Column Name | Description             | Data Type | Size | Format | Key |
| ----------- | ----------------------- | :-------- | ---- | ---- | -----
| shiftID     | Unique Shift Identifier | INT       |      |      | PK
| shiftBegin  | The shift start time    | Time      |  8   | HH:MM:SS |  |
| shiftEnd    | The shift end time      | Time      |  8   | HH:MM:SS |  |
| staffID     | Unique Staff Identifier | INT       |      |      | FK | 
| venueID     | Unique Venue Identifier | INT       |      |      | FK |

Table: Staff
| Column Name   | Description               | Data Type | Size | Format | Key |
| -----------   | ------------------------- | :-------- | ---- | ---- | -----
| staffID     | Unique Staff Identifier  | INT      |      | | PK
| firstName   | The staff's first name   | Text     | 45   | |  |
| lastName    | The staff's last name    | Text     | 45   | | |
| email       | The staff's email        | Text     | 45   | | | 
| phone       | The staff's phone number | Text     | 20   | | |
| streetAddress | The staff's street address | Text | 45   | | |
| city        | The staff's city of residence | Text  | 45 |      |  |
| state       | The staff's state of residence | Text | 45 |      |  |
| zipCode     | The staff's residence zip code | Text | 45 |      |  |
| payRate     | The staff's pay rate per hour  | Double | 5 |     | |
| plannerID   | Unique Planner Identifier  | INT |        |   | FK |

Table: Stall
| Column Name      | Description             | Data Type | Size | Format | Key |
| -----------      | ----------------------- | :-------- | ---- | ---- | -----
| stallID          | Unique Stall Identifier | INT       |      |      | PK
| flatRentalCharge | The stall's flat rental charge | Double |  |      |  |
| squareMeters     | The stall's size in square meters | Double |      |   |  |
| venueID          | Unique Venue Identifier | INT       |      |      | FK | 
| vendorID         | Unique Vendor Identifier | INT      |      |      | FK |

Table: Ticket
| Column Name    | Description             | Data Type | Size | Format | Key |
| -----------    | ----------------------- | :-------- | ---- | ---- | -----
| ticketID       | Unique Ticket Identifier | INT      |      |      | PK
| ticketPlatform | The platform that sells tickets | Text | 45 |     |  |
| ticketCost     | The cost of the ticket     | Double |      |      |  |
| seatNumber     | The seat number on ticket  | Text   |  5   |      |  | 
| attendeeID     | Unique Attendee Identifier | INT    |      |      | FK |
| concertID      | Unique Concert Identifier  | INT    |      |      | FK |

Table: Vendor
| Column Name  | Description                | Data Type | Size | Format | Key |
| -----------  | -------------------------  | :-------- | ---- | ---- | -----
| vendorID     | Unique Vendor Identifier   | INT       |      |      | PK
| vendorName   | The vendor's name          | Text      | 45   |      | |
| vendorPermit | The permit vendor requires | Text      | 45   |      | |
| vendorType   | The vendor's type of service or goods  | Text | 45   | | |

Table: Venue
| Column Name | Description              | Data Type | Size | Format | Key |
| ----------- | ------------------------ | :-------- | ---- | ----   | -----
| venueID     | Unique Venue Identifier  | INT       |      |        | PK
| venueName   | The venue's name         | Text      |  45  |        | |
| location    | The venue's location     | Text      |  45  |        | |
| capacity    | The venue's maximum capacity | INT   |      |        | | 
| mainContact | The main contact's name that helps book the venue | Text | 45 |     | |
| plannerID   | Unique Planner Identifier | INT      |      |        | FK |

## SQL Queries

```
Description: 

SELECT firstName, lastName, COUNT(ticketID) AS "Number of Tickets", SUM(ticketCost) AS "Total Cost"
FROM Attendee
JOIN Ticket ON Attendee.attendeeID = Ticket.attendeeID
GROUP BY firstName, lastName
HAVING COUNT(ticketID) > 1
ORDER BY SUM(ticketCost) DESC;

Justification:




```
