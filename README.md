# CS-361-MS-A
# Ticketmaster Microservice

This microservice fetches event data from the Ticketmaster API based on search criteria (date, city, zip code, event type). The microservice stores the data in a MySQL database and allows retrieval of event information via RESTful APIs.

## How It Works

1. **POST /events**: This endpoint retrieves event data from the Ticketmaster API based on the provided search criteria (date, city, zip, and event type) and stores the events in the database.

   - **Request Body**:
     ```json
     {
       "date": "2025-02-21",
       "city": "New York",
       "zip": "10001",
       "eventType": "Music"
     }
     ```

2. **GET /events**: This endpoint retrieves events from the database based on the provided search criteria (date, city, zip, event type).

   - **Query Parameters**:
     - `date`: The date of the event (format: `YYYY-MM-DD`)
     - `city`: The city where the event takes place
     - `zip`: The zip code of the event location
     - `eventType`: The type of event (e.g., Music, Sports)

## Requirements

- Node.js (version 12 or higher)
- MySQL Database

## Installation

1. Clone this repository to your local machine.
2. Run `npm install` to install dependencies.
3. Update the `config.js` file with your MySQL database credentials and Ticketmaster API key.
4. Create a MySQL database and the `events` table:

   ```sql
   CREATE TABLE events (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255),
     date DATE,
     city VARCHAR(100),
     zip_code VARCHAR(20),
     event_type VARCHAR(100),
     ticket_url VARCHAR(255)
   );
5. Start the microservice by writing `npm start` in the terminal

## Usage

- Use the POST /events endpoint to fetch and save event data.
- Use the GET /events endpoint to retrieve event data from the database.

## Error Handling

- If an error occurs while fetching data from the Ticketmaster API, the microservice will return a 500 error with the message.
- If an error occurs while accessing the database, the microservice will return a 500 error with the message.

## UML

<img width="2735" alt="Microservice UML" src="https://github.com/user-attachments/assets/e560f5b9-1aa9-49c8-bdf6-39b8eee09852" />


