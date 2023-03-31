
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

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |
| `api_key` | `string` | **Required**. Your API key |
| `api_key` | `string` | **Required**. Your API key |
| `api_key` | `string` | **Required**. Your API key |
| `api_key` | `string` | **Required**. Your API key |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.


## Usage/Examples

```
import Component from 'my-project'

function App() {
  return <Component />
}
```

