# Pewlett-Hackard-Analysis

## Project Overview
Bobby from Pewlett_Hackard asked for a few tables to be written in SQL to determine how many employees will be retiring by title and to identify the names of the employees who would be eligible to be part of the mentorship program. This report will summarize the analysis performed to help Bobby’s manager prepare for the “silver tsunami” (the number of current employees about to reach retirement age). 

## Results
The first query that was built in SQL was to determine the number of retiring employees by job title. Pewlett-Hackard has a total of 300,024 employees with 90,398 (30%) of them retiring. Below are the results from the query:

The results for the number of retiring employees by title:

![title_count_of_retirees]( https://github.com/fletchrk/Pewlett-Hackard-Analysis/blob/main/Screenshots/title_count_of_retirees.png)

The second query that was built in SQL was to determine the names of the employees who can participate in the mentorship program. It was determined that there are 1,940 employees eligible to participate:

The results of names of employees eligible for the mentorship program:

![list_of_mentors]( https://github.com/fletchrk/Pewlett-Hackard-Analysis/blob/main/Screenshots/list_of_mentors.png)

The results for the number of employees by title:

![count_of_mentors]( https://github.com/fletchrk/Pewlett-Hackard-Analysis/blob/main/Screenshots/count_of_mentors.png)

## Summary
### Retirement Queries
In order to determine the count of employees who were retiring, three queries were built to determine. The first query was developed by utilizing two tables to pull the data, which were the employees table, and the titles table. The tables were inner joined by the emp_no that each table contained. The fields that were queried were emp_no, first_name, last_name, title, from_date, to_date. The final two steps of the query were to filter by the employees who were born between 01-01-1952 and 12-31-1955 then was sorted by ascending order using the emp_no column. 

Unfortunately, this query showed duplicates for employees who have been in more than one position, so a second query was put together to make sure the employees were on the list in their most current position. This type of query is called a DISTINCT ON query that used the emp_no to remove duplicates.  

The third query and final query was a COUNT query that counted how many employees in their most recent job titles are about to retire. This query counted the number of employees in 7 titles were retiring. The query was grouped by the title and was sorted by the count descending.

### Mentorship Query
The mentorship query was developed by retrieving the data from three tables (employees table, dept_emp table, and the titles table). The columns used from the employees table was the emp_no, first_name, last_name and birth_date. The columns used from the dept_emp table was the from_date and to_date while the column used in the title table was the titles column. A DISTINCT ON statement was used to retrieve the first occurrence of the employee number for each set of rows defined by the ON() clause. The next step of the query was to create a new table, then join the tables. The first join was with the employees table and dept_emp table by joining the emp_no column. The second join was to join the employees table and the titles table by joining the titles column. The next step was to filter the data on the to_date column to get current employees whose birth_date are between 1-1-1965 and 12-31-1965. Wrapping up the query by sorting (ordering) the table by the emp_no.

