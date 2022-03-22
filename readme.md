### Use the patients database and perform the following query on it : ~
- 1. find no of patients grouped by hospital
- 2. find average age grouped by hosptial
- 3. find the average BMI of all patients
- 4. find average BMI grouped by Hospital
- 5. find average BMI grouped by Severity
- 6. find date (diagnosis date) wise in ascending order total no of patients
- 7. show all users who bmi is between two values ( you can decide the values ) 
- 8. show top 10 weighing patients
- 9. show second top 10 weighing patients
- 10. show count of users with name which start with B
- 11. show count of users whose name end with E
- 12. show count of users whose name have LL on it



### Solutions problem 1 : 
1. SELECT count(*) from patients group by hospital;
2. SELECT AVG(age) from patients group by hospital;
3. SELECT AVG(weight/(height*height)) AS avg_bmi FROM patients;
4. SELECT AVG(weight/(height*height)) AS avg_bmi FROM patients group by hospital;
5. SELECT AVG(weight/(height*height)) AS avg_bmi FROM patients group by severity;
6. SELECT date_of_diagnosis from patients as date group by date_of_diagnosis order by date_of_diagnosis asc;
7. SELECT patient_name, (weight/(height*height)) as bmi from patients HAVING bmi BETWEEN 0.0030 AND 0.0038;
8. SELECT patient_name,weight FROM patients order by weight desc limit 10;
9. SELECT patient_name,weight FROM patients order by weight desc limit 10,10;
10. SELECT count(*) FROM patients WHERE patient_name like 'B%';
11. SELECT count(*) FROM patients WHERE patient_name like '%E';
12. SELECT count(*) FROM patients WHERE patient_name like '%LL%';

## Problem 2
- 1.  create a country table
- it should have id, and name, id is the primary key
- 2. create a users table
- it needs to have a primary key
- id, name, country id
- id is primary key
- NOTE. country is a foreign key to country table primary key

### Solutions problem 2 :
- 1. CREATE TABLE country (  
    -> id int NOT NULL AUTO_INCREMENT, 
    -> name varchar(255) NOT NULL,
    -> PRIMARY KEY (id)
    -> );

- 2. CREATE TABLE users (
    -> user_id INT NOT NULL AUTO_INCREMENT,
    -> name varchar(255),
    -> country_id INT NOT NULL,
    -> id INT,
    -> PRIMARY KEY (user_id),
    -> FOREIGN KEY (id) REFERENCES country(id)
    -> );

### THANK YOU 😊