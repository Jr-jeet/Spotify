# Spotify 
select * from spotify.`spotify streaming performance dataset` limit 10;



alter table spotify.`spotify streaming performance dataset` 
change `Artist Name` Artist_Name text


ALTER table spotify.`spotify streaming performance dataset`
rename column `Country of Origin` to Country_of_Origin;

ALTER table spotify.`spotify streaming performance dataset`
rename column `Primary Language` to Primary_Language;

rename table spotify.`spotify streaming performance dataset` to streaming;
