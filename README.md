# Spotify 
select * from spotify.`spotify streaming performance dataset` limit 10;

alter table spotify.`spotify streaming performance dataset` 
change `Artist Name` Artist_Name text
