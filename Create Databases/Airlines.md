# Airline Information

During my Database Management Systems Concepts and Design course at Missouri State, we used Oracle SQL to create our own database. 

## Background information:
This database tracks specific flight information. It starts out with a ticket that will keep track of the customer, flight number, departure airport, and the arrival airport. 
Additionally, the flight will keep track of the departure and arrival airports, the employees working, and other important information. This information will help the airlines 
keep track of the different elements that go into a flight and ensure consistency and clarity of information between them and the customers. These simple ERD diagrams can be 
expanded upon to add entities for the company, specific planes, seat numbers, and more.

## ERD Diagrams

### ERD Level 0:
![erd0](https://github.com/user-attachments/assets/5f47caf6-87bf-46f2-8e11-660d65597458)

### ERD Level 1:
![erd1](https://github.com/user-attachments/assets/3896ab7f-4c96-4be4-b15f-fcc6d1000fef)

### ERD Level 2:
![erd2](https://github.com/user-attachments/assets/76f277fe-d74c-41c9-a111-b5c0a140e99e)

## Tables

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

### Query with a JOIN
<img width="405" alt="join" src="https://github.com/user-attachments/assets/92a32857-9c2d-49a6-81a0-09b902959950">

### Order By
<img width="378" alt="orderby" src="https://github.com/user-attachments/assets/6e0475a5-ca19-47d3-8cc0-fa2ed268cbe5">

### Group By
<img width="414" alt="groupby" src="https://github.com/user-attachments/assets/4e861f91-e47f-447c-96da-0c5c93c9e84e">

### Where
<img width="549" alt="where" src="https://github.com/user-attachments/assets/253640e5-4989-4543-9e73-d0b7d3fc2caf">

### 5th
<img width="555" alt="5th" src="https://github.com/user-attachments/assets/a2817153-93ee-4ee7-b108-1cebe5817a50">
