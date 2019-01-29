#Rédige les requêtes SQL ayant les fonctionnalités suivantes :

#Récupérer tous les albums
SELECT * FROM albums;

#Récupérer tous les albums dont le titre contient "Great" (indice)
SELECT * FROM albums WHERE Title LIKE "%Great%";

#Donner le nombre total d'albums contenus dans la base (sans regarder les id bien sûr)
SELECT COUNT (Title) FROM albums;

#Supprimer tous les albums dont le nom contient "music"
DELETE From albums WHERE Title LIKE "%music%";

#Récupérer tous les albums écrits par AC/DC
SELECT * FROM albums WHERE ArtistId=1;

#Récupérer tous les titres des albums de AC/DC
SELECT * FROM tracks WHERE Composer="AC/DC";

#Récupérer la liste des titres de l'album "Let There Be Rock"
SELECT * FROM tracks WHERE AlbumId=4;

#Afficher le prix de cet album ainsi que sa durée totale
SELECT SUM(UnitPrice) FROM tracks WHERE AlbumId=4;
SELECT SUM(Milliseconds) FROM tracks WHERE AlbumId=4;
marche pas > SELECT SUM(Milliseconds) AND SUM(UnitPrice) FROM tracks WHERE AlbumId=4;

#Afficher le coût de l'intégralité de la discographie de "Deep Purple"
SELECT * FROM artists;
SELECT Name FROM artists ORDER BY Name;
SELECT * FROM artists WHERE Name LIKE "%Deep Purple%";
SELECT * FROM albums WHERE ArtistId=58;
SELECT * FROM tracks;
marche pas > SELECT * FROM tracks WHERE Composer="Deep Purple";

SELECT * FROM tracks WHERE AlbumId = 43 OR AlbumId = 50 OR AlbumId = 58 OR AlbumId = 59 OR AlbumId = 60 OR AlbumId = 61 OR AlbumId = 62 OR AlbumId = 63 OR AlbumId = 64 OR AlbumId = 65 OR AlbumId = 66;

SELECT SUM(UnitPrice) FROM tracks WHERE AlbumId = 43 OR AlbumId = 50 OR AlbumId = 58 OR AlbumId = 59 OR AlbumId = 60 OR AlbumId = 61 OR AlbumId = 62 OR AlbumId = 63 OR AlbumId = 64 OR AlbumId = 65 OR AlbumId = 66;

SELECT SUM(Milliseconds) FROM tracks WHERE AlbumId = 43 OR AlbumId = 50 OR AlbumId = 58 OR AlbumId = 59 OR AlbumId = 60 OR AlbumId = 61 OR AlbumId = 62 OR AlbumId = 63 OR AlbumId = 64 OR AlbumId = 65 OR AlbumId = 66;

#Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks
INSERT INTO artists(Name) VALUES('Mastodon');
SELECT * FROM artists;
SELECT Name FROM artists ORDER BY Name;

SELECT * FROM albums;
.schema albums
INSERT INTO albums(Title, ArtistId) VALUES('The Hunter',276);

SELECT * FROM tracks;
.schema tracks
SELECT * FROM genres;
metal = 3
SELECT * FROM media_types;
MPEG audio file = 1

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('Black Tongue', 348, 1, 'Mastodon', 999999, 8888, 0.99);

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('Curl Of The Burl', 348, 1, 'Mastodon', 999999, 8888, 0.99);

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('Blasteroid', 348, 1, 'Mastodon', 999999, 8888, 0.99);

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('Stargasm', 348, 1, 'Mastodon', 999999, 8888, 0.99);

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('Octopus Has No Friends', 348, 1, 'Mastodon', 999999, 8888, 0.99);

INSERT INTO tracks(Name, AlbumId, MediaTypeId, Composer, Milliseconds, Bytes, UnitPrice) VALUES ('All The Heavy Lifting', 348, 1, 'Mastodon', 999999, 8888, 0.99);
