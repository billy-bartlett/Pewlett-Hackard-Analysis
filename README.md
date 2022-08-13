# Pewlett-Hackard-Analysis

## Overview

For this analysis, I was tasked with determining the number of retiring employees by title and identifying employees who are eligible to participate in a mentorship program. The mentorinship program aims to keep retirement aged employees on staff part-time to mentor junior employees. To complete this analysis, I utlized SQL queries to create tables, import data from csvs into tables, manipulate tables with joins and functions, and export data into csvs.

## Results 
Through my analysis, I was able to identify four key insights:

1. I identified a list of employees eligible for retirement by title. This list returned many duplicate employees due to promotions and new tours of duty within the company so the list required manipulation to increase clarity.

2. I then removed duplicate employees to ensure an accurate list. Looking at the "unique_titles" csv, we can now see the correct sum and respective titles for the retiring employees. 74,458 employees are set to retire! 

3. With so many employees retiring, it became clear I needed to get an accurate count for each department. With this in mind, I created the "retiring_titles" table. This gives us a count which helps us determine which departments will be affected and the level of that impact. The count is as follows: 25,916 from Senior Engineering, 24,926 from Senior Staff, 9,285 from Engineer, 7,636 from Staff, 3,603 from Technique Leader, 1,090 from Assistant Engineer, and 2 from Manager. 

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_employees_table.png)

4. Next, I needed to determine the number of employees that were eligible for the Mentorship Eligibility Program to counteract the wave of retirees. I sorted through the employee databases to identify individuals with a birth date in 1965. These individuals are the next wave to retire and have the most experience along with a strong skillset they can use to mentor junior employees. The "mentorship_eligibility" csv contains a list of every employee suited for the mentorship program.

To dig even deeper, once I completed a count of the mentorship eligibility by title, I calculated the following counts: 432 from Senior Staff, 404 from Engineer, 292 from Staff, 284 from Senior Engineer, 77 from Technique Leader, and 60 from Assistant Engineer. An interesting takeaway from this table is that there are no Managers who fall in the 1965 year parameter that was set. This means the program would need to expand the years to include employees with the Manager title.

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Mentorship_employees_count_table.png)

## Summary

When setting out to complete this analysis, there were two main asks:
1. Determine the number of retiring employees per title
2. Identify a list of employees who are eligible to participate in a mentorship program

Determining the number of retiring employees per title required multiple steps. I first created a table for all employees eligible for retirement. I then removed the duplicate entries using the "DISTINCT ON" function to create a new table. Lastly, I used the COUNT function to get a count of employees retiring from each department. See the code and the table below for reference. 

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_employees_code.png)

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Retirement_employees_table.png)

To identify a list of employees eligible to participate in the mentorship program, I joined three tables: employees, department_employees, and titles. I selected only the employees with birth dates between 1-1-1965 and 12-31-1965. I also only pulled employees who were currently employeed. See the code and the table below for reference. Please note, the table only displays the first 10 employees eligible to participate in the mentorship program. For an all-inclusive list, please see the csv titled "mentorship_eligibility."

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Employees_eligible_to_mentor.png)

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Mentorship_program_table%20.png)


One last thing I wanted to analyze was the number of employees that may be well suited for mentorship by senior employees. I decided employees who have been in their current position for 3 years or less would provide a good pool of candidates who may benefit from mentoring. To identify this pool, I created a view table that held all employees that fit my parameter. I then created a query to return these individuals in a table and set the "from_date" to descending order. Ordering the table this way allows us to see the employees who have been in their positions the least amount of time at the top of the table. 

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Employees_eligible_for_mentorship.png)

![picture alt](https://github.com/billy-bartlett/Pewlett-Hackard-Analysis/blob/main/Resources/Employees_eligible_for_mentorship_table.png)

