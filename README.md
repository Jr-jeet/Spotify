# Spotify Streaming analysis

<img width="128" height="128" alt="image" src="https://github.com/user-attachments/assets/fb8d75fd-09c7-483c-b6bc-729a44b2a4b1" />

# Identifying the data
select * from spotify.`spotify streaming performance dataset` limit 10;


# Changing the column names 
alter table spotify.`spotify streaming performance dataset` 
change `Artist Name` Artist_Name text


# Changing the column names 

ALTER table spotify.`spotify streaming performance dataset`
rename column `Country of Origin` to Country_of_Origin;


# Changing the column names 

ALTER table spotify.`spotify streaming performance dataset`
rename column `Primary Language` to Primary_Language;



# Changing the table names 
use spotify;
rename table `spotify streaming performance dataset`
to streaming;

ALTER table `streaming` 
rename column `Primary Genre` to Primary_Genre;


ALTER table `streaming` 
rename column `Artist Type` to Artist_Type;

SELECT * FROM streaming  limit 10;





ALTER table `streaming`
rename column `Debut Year` to Debut_Year;

alter table `streaming`
rename column `Total Streams (in millions)`  to  Total_Streams;

alter table `streaming`
rename column `Lead Streams (in millions)`  to  Lead_Streams;

alter table `streaming`
rename column `Feature Streams (in millions)`  to  Feature_Streams;

alter table `streaming`
rename column `Solo Streams (in millions)`  to  Solo_Streams;

alter table `streaming`
rename column `% of Solo Streams`  to  percentage_of_Solo_Streams;

alter table `streaming`
rename column `Collaborative Streams (in millions)`  to  Collaborative_Streams;

alter table `streaming`
rename column `% of Collaborative Streams`  to  precentage_of_Collaborative_Streams;

#Here all the column now be ok#

use spotify;
select * from streaming limit 10;

select count(*),Country_of_Origin
from streaming
group by Country_of_Origin
order by count(*) DESC;

select count(*),Primary_Language
from streaming
group by Primary_Language
order by count(*) DESC;

select count(*),Primary_Genre
from streaming
group by Primary_Genre
order by count(*) DESC;

select count(*),Artist_Type
from streaming
group by Artist_Type
order by count(*) DESC;

select count(*),Debut_Year
from streaming
group by Debut_Year
order by count(*) DESC;


SELECT Artist_Name, Total_Streams
FROM streaming
ORDER BY Total_Streams DESC
LIMIT 10;


select Artist_Name as AR,Solo_Streams,Collaborative_Streams
from streaming
where percentage_of_Solo_Streams <= precentage_of_Collaborative_Streams 
order by  Collaborative_Streams DESC 
;

# SUM OF MOST GENRE GENERATE THE MOST TOTAL STREAMS?
select  Primary_Genre,sum(Total_Streams)
from streaming
group by Primary_Genre
order by  sum(Total_Streams) DESC 
;

# MAX GENRE GENERATE THE MOST TOTAL STREAMS?
select  Primary_Genre,MAX(Total_Streams)
from streaming
group by Primary_Genre
order by  MAX(Total_Streams) DESC 
;

# WHICH GENRES HAS THE HIGHESTT % OF COLLABRATIVE STEAMS?
select  Primary_Genre, avg(precentage_of_Collaborative_Streams) as avg_precentage_of_Collaborative_Streams
from streaming
group by Primary_Genre
order by avg_precentage_of_Collaborative_Streams DESC
;

# which type  of artist 
select count(Primary_Genre),Artist_Type
from streaming
group by Artist_Type
;

#  MOST LEAD STREAMING ARTIST NAME
select max(Lead_Streams),Artist_Name
from streaming
group by Artist_Name
order by max(Lead_Streams) DESC
;




