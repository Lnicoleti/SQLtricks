# SQLtricks

-- 1
-- What are the column names?
SELECT *
FROM transaction_data
LIMIT 10;

-- 2
-- Find the full_names and emails
-- of the transactions listing 20252 as the zip code.
SELECT full_name, email, zip
FROM transaction_data
WHERE zip = 20252;
-- 3
-- Use a query to find the names 
-- and emails associated with these transactions.
SELECT full_name, email
FROM transaction_data
WHERE full_name = 'Art Vandelay'
   OR full_name LIKE '% der %';

-- 4
-- Find the ip_addresses and emails listed with these transactions.
SELECT ip_address, email
FROM transaction_data
WHERE ip_address LIKE '10.%';

-- 5
-- Find the emails in transaction_data with
-- ‘temp_email.com’ as a domain.
SELECT email
FROM transaction_data
WHERE email LIKE '%temp_email.com';

-- 6
-- The finance department is looking for a specific transaction. 
-- They know that the transaction occurred from an ip address starting 
-- with ‘120.’ and their full name starts with ‘John’.

-- Can you find the transaction?
SELECT *
FROM transaction_data
WHERE full_name LIKE 'John%'
  AND ip_address LIKE '120.%';

------- part 2 ----------

-- 1
-- What are the column names?
SELECT *
FROM users
LIMIT 20;
 
-- 2
-- Find the email addresses and birthdays of users whose 
-- birthday is between 1980-01-01 and 1989-12-31.
   SELECT email, birthday
FROM users
WHERE birthday >= '1980-01-01'
  AND birthday <= '1989-12-31';
-- 3
-- Find the emails and creation date of users 
-- whose created_at date matches this condition.

SELECT email, created_at
FROM users
WHERE created_at < '2017-05-01';
-- 4
-- Find the emails of the users who received the ‘bears’ test.
SELECT email
FROM users
WHERE test = 'bears';

-- 5
-- Find all the emails of all users who 
-- received a campaign on website BBB.

SELECT email
FROM users
WHERE campaign LIKE 'BBB%';

-- 6
-- Find all the emails of all users who received ad copy 2 in 
-- their campaign.
SELECT email
FROM users
WHERE campaign LIKE '%-2';

-- 7
-- Find the emails for all users who received both a campaign and a test. 
-- These users will have non-empty entries in the 
-- campaign and test columns.
SELECT email
FROM users
WHERE campaign IS NOT NULL
  AND test IS NOT NULL;

