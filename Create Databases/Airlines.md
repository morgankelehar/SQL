# Airline

During my Database Management Systems Concepts and Design course at Missouri State, we used Oracle SQL to create our own database. This project was divided into three sections, ERD diagrams, tables, and queries. Each section had a list of requirements that were necessary as well as an explanation. Additional discriptions are provided throughout the document showcasing this information.

## Background information:
This database tracks specific flight information. It starts out with a ticket that will keep track of the customer, flight number, departure airport, and the arrival airport. 
Additionally, the flight will keep track of the departure and arrival airports, the employees working, and other important information. This information will help the airlines 
keep track of the different elements that go into a flight and ensure consistency and clarity of information between them and the customers. These simple ERD diagrams can be 
expanded upon to add entities for the company, specific planes, seat numbers, and more.

## Entity Relationship Diagrams (ERD)
I used LucidChart to create three ERD diagrams to help with the creation of my 'Airlines' database. 

### ERD Level 0:
I started with an ERD level 0 diagram to show the main entities and their relationships to one another with the data used. I ended up with five entities (that will become tables) in my database; customer, ticket, airport, flight, and employees.
![erd0](https://github.com/user-attachments/assets/5f47caf6-87bf-46f2-8e11-660d65597458)

### ERD Level 1:
For the level 1 ERD diagram, I expanded upon the level 0 by adding the attributes (columns) that would be represented in each table. The level 1 diagram further establishes the relationships between the entities with the introduction of the primary and foreign keys. There is also an introduction to the 'Employee Details' entity which serves as a connector to the flight and employee tables due to there fact that each employee has many flights.
![erd1](https://github.com/user-attachments/assets/3896ab7f-4c96-4be4-b15f-fcc6d1000fef)

### ERD Level 2:
The ERD level 2 diagram is very similar to the level 1 except it adds in the data type for each attribute. This helps form the transition from the ERD diagrams into the actual creation of the table in the database. Based on the data that would be represented in each field (column), the appropriate data type is choses. This is important for future steps when data is imported as it allows potential errors to be recognized. 
![erd2](https://github.com/user-attachments/assets/76f277fe-d74c-41c9-a111-b5c0a140e99e)

## Tables
For the tables section of the project, I used entities and relationships created in the ERD diagrams to create these tables. Each table was created with a primary key and each attribute had a corresponding datatype. Once the table was created, I inserted 10 rows of data for each table, making sure that the datatypes were followed as stated in the ERD diagrams. For each table I have attatched an image of the code to create the table and the corresponding description, the code to insert a row of data (one out of the ten was selected), and an image showing all of the rows of data in the table.

### Customers Table:
<img width="376" alt="customers1" src="https://github.com/user-attachments/assets/e827f099-9a26-4bd5-aa61-484d8a243263">
<img width="549" alt="customers2" src="https://github.com/user-attachments/assets/3856b7b0-f51a-4bab-a4ef-781726a54eaa">

INSERT INTO mk_customers (customer_id, password, first_name, last_name, phone_number, email, address, city, state, zip_code) VALUES ('BA17283959', 'WildTacos20', 'Brian', 'Alderman', '8164481263', 'brianalderman@gmail.com', '1110 N Highway Ave', 'Kansas City', 'MO', '64151');

### Airport:
<img width="404" alt="airport1" src="https://github.com/user-attachments/assets/cfab601f-013f-49c0-ae96-2fec5c3684ab">
<img width="549" alt="airport2" src="https://github.com/user-attachments/assets/076b0ad4-a173-46eb-8d71-e62e3eadffb9">

INSERT INTO mk_airport (airport_id, name, phone_number, address, city, state, zip_code) VALUES ('MCI', 'Kansas City International Airport', '8162435237', '1 Kansas City Blvd', 'Kansas City', 'MO', '64153');

### Flight
<img width="393" alt="flight1" src="https://github.com/user-attachments/assets/55fd91f3-125a-41fb-8e10-3787d70b041d">
<img width="450" alt="flight2" src="https://github.com/user-attachments/assets/881ec165-3b9a-410c-aac3-0d48fa9cd423">

INSERT INTO mk_flight (flight_number, company_id, total_seats, total_passengers, plane_id) VALUES ('WN1736', 'SW', 143, 126, 'N8539V'); 

### Employee
<img width="386" alt="employee1" src="https://github.com/user-attachments/assets/c946885e-1bf8-42fe-ae53-b3f55698398a">
<img width="549" alt="employee2" src="https://github.com/user-attachments/assets/e270d8a1-e12f-486c-9226-057a615d07fb">

INSERT INTO mk_employee (employee_id, password, first_name, last_name, position_title, phone_number, email, start_date) VALUES ('JC85438906', 'IlikePlan3s!', 'Janet', 'Conner', 'First Officer', '8173245678', 'janetconner@gmail.com', '08-FEB-2005');

### Employee Details
<img width="406" alt="employeedetails1" src="https://github.com/user-attachments/assets/7cadff69-6439-4eba-ac60-ad7def123c98">
<img width="416" alt="employeedetails2" src="https://github.com/user-attachments/assets/1e1cb7cd-0b8a-4266-8f06-9737ed152fd6">

INSERT INTO mk_employee_details (flight_number, employee_id, position_title) VALUES ('WN1736', 'MB68300791', 'Captain');

### Ticket
<img width="327" alt="ticket1" src="https://github.com/user-attachments/assets/5cd49ac7-f8ee-4278-ba76-0026e4178d80">
<img width="213" alt="ticket2" src="https://github.com/user-attachments/assets/008b0e17-562e-4eb2-b38d-285813af5f78">
<img width="540" alt="ticket3" src="https://github.com/user-attachments/assets/847d3902-7ef7-46d2-9b28-abb5bdee6b03">

INSERT INTO mk_ticket (ticket_id, customer_id, flight_number, first_name, last_name, seat_number, gate_number, depart_airport_id, arriv_airport_id) VALUES ('GM43F', 'BA17283959', 'WN1736', 'Brian', 'Alderman', '17B', 'A28', 'MCI', 'TPA');

## Example Queries

The third part of this project was to run five queries with my database. I had guidelines of what query type to use but I got to choose what went into it.

### JOIN Query
For the query with a 'JOIN', I used a 'NATURAL JOIN' to join the 'Employee' and 'Employee Details' together. I chose to use a 'NATURAL JOIN' as it ensures there aren't any duplicates and I was able to join them due to the column match of 'employee_id'. In this query I wanted to know the flight number, employee id, first name, and last name of the the employee. This helped to show what flight numbers employees were assigned to. In further queries, I could be able to see the employee's contact information, flight information, airport information, and what customers would be on that flight. 

<img width="405" alt="join" src="https://github.com/user-attachments/assets/92a32857-9c2d-49a6-81a0-09b902959950">

### ORDER BY
For the 'ORDER BY" statement query, I kept it simple by ordering customers by their last name in ascending order. This was a simple query but can be included in a variety of different queries and attributes.

<img width="378" alt="orderby" src="https://github.com/user-attachments/assets/6e0475a5-ca19-47d3-8cc0-fa2ed268cbe5">

### GROUP BY
In the 'GROUP BY' statement query, I wanted to know how many aiports in each state is an international airport. I used the 'COUNT(*)' function to count how many rows and the 'GROUP BY' statement to count by each state. To ensure that the query was only selecing international aiports, I included a 'LIKE' operation and used the percent symbol (%) as my wild card at the start and end to ensure that the row matches. With a larger dataset, the foundations of this query can be expanded to many other queries like how many flights someone has been on, how many employees, and how many passengers are on a flight.

<img width="414" alt="groupby" src="https://github.com/user-attachments/assets/4e861f91-e47f-447c-96da-0c5c93c9e84e">

### WHERE
I used the 'WHERE' statement query to find out what flight numbers arrived to or departed from Kansas City International Aiport (MCI designation). I used the 'LIKE' operation again to find the rows that matched the condition of having 'MCI' in there arrival or departure airport. The 'WHERE' statement can be used in many queries due to the versitility of it. I used it in majority of my example queries in this database.

<img width="549" alt="where" src="https://github.com/user-attachments/assets/253640e5-4989-4543-9e73-d0b7d3fc2caf">

### Custom Query
For my last query, I got to do whatever I wanted to. I decided to utilize the 'WHERE' and 'ORDER BY' statements to find out how many seats were available on each flight. Using the flight table, I created a statement to include flight numbers were the seats remaining was 15 or less in ascending order. The equation used was 'total_seats - total passengers <= 15'. I also had to use a column alias to creat a new column called 'SEATS_AVAILABLE' to see how manys seats were available for each flight. The foundations of this query can be used in many instances for example; how many employees are still needed for a flight.

<img width="555" alt="5th" src="https://github.com/user-attachments/assets/a2817153-93ee-4ee7-b108-1cebe5817a50">

## Final Thoughts
This project was a lot of fun to create and I learned a lot from having to apply what I learned in class to a real world example. I had to do a lot of problem solving when creating this project due to the complex nature of creating a database from scratch. This project allowed me to make mistakes and find solutions to future issues. In the future, I would love to expand on this project with a larger data set and more entities to get practice running more complex queries.
