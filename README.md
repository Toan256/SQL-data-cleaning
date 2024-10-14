# SQL-data-cleaning
This is an educational project on data cleaning and preparation using SQL. The original database in CSV format is located in the file club_member_info.csv. Here, we will explore the steps that need to be applied to obtain a cleansed version of the dataset.
SELECT*FROM club_member_info cmi LIMIT 10

# Create new table
CREATE TABLE club_member_info_cleaned (
	full_name VARCHAR(50),
	age INTEGER,
	martial_status VARCHAR(50),
	email VARCHAR(50),
	phone VARCHAR(50),
	full_address VARCHAR(50),
	job_title VARCHAR(50),
	membership_date VARCHAR(50)
);

# Copy the table
insert into club_member_info_cleaned
select*from club_member_info ;

# Data cleaning
select trim(proper(full_name)) as name from club_member_info_cleaned cmic;
update club_member_info_cleaned 
set full_name = trim(proper(full_name));
SELECT*FROM club_member_info_cleaned where age between 0 and 100;
DELETE FROM club_member_info_cleaned where martial_status IS NULL ;
SELECT*FROM club_member_info_cleaned
