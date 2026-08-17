# Spotify 
select * from spotify.`spotify streaming performance dataset` limit 10;



alter table spotify.`spotify streaming performance dataset` 
change `Artist Name` Artist_Name text


ALTER table spotify.`spotify streaming performance dataset`
rename column `Country of Origin` to Country_of_Origin;

ALTER table spotify.`spotify streaming performance dataset`
rename column `Primary Language` to Primary_Language;

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


select count(*),Debut_Year
from streaming
group by Debut_Year
order by count(*) DESC;



