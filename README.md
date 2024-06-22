# PetSQLQueries

Welcome to the PetSQLQueries repository! This project is designed to help you enhance your SQL querying skills through practical exercises focused on managing data related to pets, their owners, and veterinary procedures.

## Repository Content

### 1. SQL Queries

This repository includes a set of SQL queries that cover various scenarios related to pets and their owners. Each query is designed to address specific tasks and challenges commonly encountered in data management and analysis. Below are some examples of the types of SQL queries you will find:

#### Example Queries:



**Query 1:** List the names of all pet owners along with the names of their pets.
Inner Join
```sql

select pets.Name as pet_name,petowners.Name as Pet_Owner
from petowners join pets on petowners.OwnerID=pets.OwnerID;
```

**Query 2:** List all pets and their owner names, including pets that don't have recorded owners.
Left Join
```sql
select pets.Name as pet_name,petowners.Name as Pet_Owner
from pets left join petowners on petowners.OwnerID=pets.OwnerID;
```

**Query 3:** For each pet, display the pet's name, the number of procedures they've had, and a status label:
'Regular' for pets with 1 to 3 procedures, 'Frequent' for 4 to 7 procedures, and 'Super User' for more
than 7 procedures.
```sql
select pets.Name,count(procedureshistory.procedureType) as Procedures_Count,
CASE
when count(procedureshistory.procedureType) between 1 and 3 then 'Regular'
when count(procedureshistory.procedureType) between 4 and 7 then 'Frequent'
when count(procedureshistory.procedureType) >7 then 'Super User'
end as status_label
from pets
left join procedureshistory on pets.petID=procedureshistory.petID
group by procedureType,pets.Name
;
```

### 2. Data Files

The repository includes CSV files that serve as data sources for the SQL queries. These files contain detailed information about pets, their owners, and the veterinary procedures performed on the pets. You can use these files to populate your database or practice querying directly from CSVs.

### 3. Assessment Tasks

Use the csv files provided for data and solve the following queries:
1. List the names of all pet owners along with the names of their pets.

2. List all pets and their owner names, including pets that don't have recorded owners.

3. Combine the information of pets and their owners, including those pets without owners and owners without pets.
4. List all pet owners and the number of dogs they own.
5. Identify pets that have not had any procedures.
6. Find the name of the oldest pet.
7. Find the details of procedures performed on 'Cuddles'.
8. List the pets who have undergone a procedure called 'VACCINATIONS'.
9. Count the number of pets of each kind.
10. Group pets by their kind and gender and count the number of pets in each group.
11. Show the average age of pets for each kind, but only for kinds that have more than 5 pets.
12. Find the types of procedures that have an average cost greater than $50.
13. Classify pets as 'Young', 'Adult', or 'Senior' based on their age. Age less then 3 Young, Age between 3and 8 Adult, else Senior.
14. Show the gender of pets with a custom label ('Boy' for male, 'Girl' for female).
15. For each pet, display the pet's name, the number of procedures they've had, and a status label: 'Regular' for pets with 1 to 3 procedures, 'Frequent' for 4 to 7 procedures, and 'Super User' for more than 7 procedure
### 4. Hints and Tips

To assist you in mastering SQL concepts and handling more complex queries, the repository offers additional hints and tips. These include strategies for optimizing queries, handling NULL values, and addressing common challenges encountered in SQL, such as performance issues and syntax variations across different database systems.

## Key Features

- **Practice Complex Joins:** Learn to combine data from multiple tables using various join techniques (e.g., INNER JOIN, LEFT JOIN).
  
- **Data Aggregation:** Master the use of aggregation functions (e.g., COUNT, SUM, AVG) to summarize and analyze data effectively.

- **Conditional Logic:** Implement conditional statements (e.g., CASE WHEN) to categorize data and generate custom labels based on specific conditions.

- **Real-World Scenarios:** Apply SQL skills to practical scenarios involving pet data management, preparing you for real-world data analysis tasks.

## Who Is This For?

This repository is ideal for:

- **Students:** Enhance your SQL skills through hands-on exercises that simulate real-world data scenarios.
  
- **Data Analysts:** Practice querying and analyzing data related to pets and owners, improving your proficiency in SQL.
  
- **Developers:** Strengthen your database management skills and SQL query optimization techniques.

## Getting Started

To get started with PetSQLQueries, follow these steps:

1. **Clone the repository** to your local machine or download the ZIP file.
   
2. **Set up your database:** Use the provided SQL scripts or import the CSV files into your preferred SQL database management system (e.g., MySQL, PostgreSQL).
   
3. **Explore the queries:** Review the assignment tasks and execute the SQL queries against your database to practice and reinforce your SQL skills.



By engaging with the PetSQLQueries repository, you'll gain valuable hands-on experience in SQL querying and data management, preparing you for a wide range of data-related tasks in your academic, professional, or personal projects. Happy querying!

