# My-SQL_Sample
Practicing my sql knowledge in the real -world datasets
## SOLVING SCENARIO BASED SQL QUESTIONS ON HACKERRANK ## 
- PROBLEM STATEMENT 1- You are given two tables: Students and Grades. Students contains three columns ID, Name and Marks.Grades contains the following data:grade min_marks max_marks
Ketty gives Eve a task to generate a report containing three columns:  Name, Grade and Mark. 
Ketty doesn't want the NAMES of those students who received a grade lower than 8. 
The report must be in descending order by grade -- i.e. higher grades are entered first. 
If there is more than one student with the same grade (1-10) assigned to them, order those particular students by their name alphabetically. 
Finally, if the grade is lower than 8, use "NULL" as their name and list them by their marks in ascending order.

Write a query to help Eve.
- SOLUTION :- SELECT
              CASE WHEN grad.grade <=8 THEN std.name
                   ELSE NULL
                   END
  grad.grade,std.name from students,grades
  LEFT JOIN Grades ON (std.marks BETWEEN grad.min_marks AND grad.max.marks)
  ORDER BY grad.grades DESC, std.name ASC;
