# LeanPlatform Task BE3
Session/Slot Management Spring Boot Project for Lean Platform Technologies

Session Management BE3 Task Project succesfully completed on Spring Boot having all Api's as below mentioned and Service as well As RestController also tested to ensure the sanctity of my code.

# REST API Documentation -

## 1. Introduction

This Spring Boot application exposes a set of RESTful APIs for managing sessions, session details, pre-session activities, and feedback. The APIs are intended to be used by clients and consultants.

## 2. API Endpoints

### 2.1. Slot/Session Booking API

#### 2.1.1. Book Session

- **Endpoint**: `POST /session`
- **Description**: Allows clients or consultants to book a session.
- **Request Body**: JSON representation of a `Slot` object.
- **Response**: Returns a `Slot` object with session booking details.
- **HTTP Status Codes**:
  - `201 Created`: The session was booked successfully.
  {
  "id": 0,
  "client": {
    "id": 1
  },
  "consultant": {
    "id": 1
  },
  "dateTime": "2023-09-20T10:15:57.086Z"

}

### 2.2. Session/Slot Details APIs

#### 2.2.1. Get Consultant's Upcoming Sessions

- **Endpoint**: `GET /consultant_Upcoming_Sessions/{consultantId}`
- **Description**: Allows consultants to retrieve their upcoming sessions.
- **Path Variable**: `consultantId` - ID of the consultant.
- **Response**: Returns a list of `Slot` objects representing upcoming sessions.
- **HTTP Status Codes**:
  - `202 Accepted`: Sessions retrieved successfully.
{
    "id": 1,
    "client": {
      "id": 1,
      "name": "Tilu",
      "occupation": "Student",
      "contact": "1679679679",
      "address": "Solan,HP"
    },
    "consultant": {
      "id": 1,
      "name": "Dr. Aditya",
      "contact": "434343434"
    },
    "dateTime": "2023-09-20T10:15:57.086"
  }


#### 2.2.2. Get Client's Session History

- **Endpoint**: `GET /client_Sessions_History/{clientId}`
- **Description**: Allows clients to retrieve their session history.
- **Path Variable**: `clientId` - ID of the client.
- **Response**: Returns a list of `Slot` objects representing session history.
- **HTTP Status Codes**:
  - `202 Accepted`: Session history retrieved successfully.
  {
    "id": 1,
    "client": {
      "id": 1,
      "name": "Tilu",
      "occupation": "Student",
      "contact": "1679679679",
      "address": "Solan,HP"
    },
    "consultant": {
      "id": 1,
      "name": "Dr. Aditya",
      "contact": "434343434"
    },
    "dateTime": "2023-09-20T10:15:57.086"
  }


### 2.3. Pre-session Activities APIs

#### 2.3.1. Select List of Documents for a Session (Consultants)

- **Endpoint**: `POST /select_List_Of_Document_For_A_Session`
- **Description**: Allows consultants to specify the list of documents needed for a session.
- **Request Body**: JSON representation of a `Document` object.
- **Response**: Returns a `Document` object with document selection details.
- **HTTP Status Codes**:
  - `201 Created`: Documents selected successfully.
{
  "id": 0,
  "listOfDocuments": [
"Aadhar","Pan"
],
  "slot": {
    "id": 1
  }
}


#### 2.3.2. Get Documents Needed for a Session (Clients)

- **Endpoint**: `GET /documents_Needed_For_Session/{sessionId}`
- **Description**: Allows clients to retrieve the details of documents required for a specific session.
- **Path Variable**: `sessionId` - ID of the session.
- **Response**: Returns a list of document names.
- **HTTP Status Codes**:
  - `202 Accepted`: Documents retrieved successfully.
 [ "Aadhar", "Pan" ]


#### 2.3.3. Get List of All Documents (Consultants)

- **Endpoint**: `GET /all_documents`
- **Description**: Allows consultants to view a list of all documents.
- **Response**: Returns a list of `Document` objects representing all documents.
- **HTTP Status Codes**:
  - `202 Accepted`: Documents retrieved successfully.
{
    "id": 1,
    "listOfDocuments": [
      "Aadhar",
      "Pan"
    ],
    "slot": {
      "id": 1,
      "client": {
        "id": 1,
        "name": "Tilu",
        "occupation": "Student",
        "contact": "1679679679",
        "address": "Solan,HP"
      },
      "consultant": {
        "id": 1,
        "name": "Dr. Aditya",
        "contact": "434343434"
      },
      "dateTime": "2023-09-20T10:15:57.086"
    }
  },
  {
    "id": 2,
    "listOfDocuments": [
      "Aadhar",
      "Pan",
      "MentorId",
      "BuisnessId"
    ],
    "slot": {
      "id": 2,
      "client": {
        "id": 1,
        "name": "Tilu",
        "occupation": "Student",
        "contact": "1679679679",
        "address": "Solan,HP"
      },
      "consultant": {
        "id": 2,
        "name": "Dr. Harsh",
        "contact": "434343434"
      },
      "dateTime": "2023-09-21T01:30:00.109"
    }
  }

### 2.4. Upload Feedback APIs

#### 2.4.1. Post Feedback by Consultant for Client

- **Endpoint**: `POST /feedback`
- **Description**: Allows consultants to provide feedback based on a session to a client.
- **Request Body**: JSON representation of a `Review` object.
- **Response**: Returns a `Review` object with feedback details.
- **HTTP Status Codes**:
  - `201 Created`: Feedback posted successfully.
{
  "id": 0,
  "client": {
    "id": 1
  },
  "consultant": {
    "id": 1
  },
  "feedback": "He is a good guy"
}

#### 2.4.2. Get Feedback for Client

- **Endpoint**: `

GET /feedback/{clientId}/{consultantId}`
- **Description**: Allows clients to see the feedback provided by a consultant.
- **Path Variables**:
  - `clientId` - ID of the client.
  - `consultantId` - ID of the consultant.
- **Response**: Returns feedback provided by the consultant.
- **HTTP Status Codes**:
  - `202 Accepted`: Feedback retrieved successfully.
He is a good guy

And for all Api's `400` error with respective response bodies in case of some failure.
---
This Project has been successfully tested for Apis' as well as service logic and Clean Code as well as best practices were used.
In Memory Database - H2
Port - 1000
#-------------------
Hope I succeeded in meeting your expectations,Looking forward to work with Lean Platform Technologies.
Thank You
Abhinav Vashishth
