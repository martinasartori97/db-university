- 1:
 select *
 from students
 where year (date_of_birth) = 1990	  (160 row)

 - 2:
 SELECT * 
 from courses 
 WHERE cfu > 10	 (479 row) 

 - 3:
 select *
from students
where date_of_birth > 30;

- 4:
select * 
from courses
where period = 'I semestre' And year = 1;

- 5:
select * 
from exams
where date = '2020-06-20' and hour > '14:00:00';

- 6:
select *
from degrees
where level = 'magistrale';

- 7:
?



- 8:
select *
from teachers 
Where isnull(phone);

- 9:
insert into db_university.students (degree_id, name, surname, date_of_birth, fiscal_code, enrolment_date, registration_number, email)
values (27,'martina','sartori','30-04-1997','srtmtn97d70f032j','2025-15-07','22222','dodo30@.com');

- 10:




- 11:



 