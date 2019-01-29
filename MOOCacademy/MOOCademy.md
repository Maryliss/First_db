#création fichier:
sqlite3 moocacademy.sqlite

#création de la tab courses
CREATE TABLE 'Courses' ('IDCourse' integer primary key autoincrement, 'Title' text, 'Description' text);

#création d'une 1ère entrée pour la tab courses
insert into Courses (Title, Description) values ('Cours de dessin', 'Apprendre à dessiner avec des pastels');

#création d'une 2ème entrée pour la tab courses
insert into Courses (Title, Description) values ('Cours de chant', 'Apprendre à chanter avec sa bouche');

#mise en page sympa
.header on
.mode column

#affichage de la tab courses
SELECT * FROM Courses;

#création de la tab lessons
CREATE TABLE 'Lessons' ('IDLesson' integer primary key autoincrement, 'Title' text, 'Body' text, 'IDCourse', FOREIGN KEY (IDCourse) REFERENCES Courses(IDCourse));

#création d'une 1ère entrée pour la tab lessons
INSERT INTO Lessons (Title, Body, IDCourse) VALUES ('Quest-ce qu une pastel', 'Ou les acheter?',1);

#création d'une 2ème entrée pour la tab lessons
INSERT INTO Lessons (Title, Body, IDCourse) VALUES ('Quest-ce qu une feuille', 'Comment les  choisir',1);

#création d'une 3ème entrée pour la tab lessons
INSERT INTO Lessons (Title, Body, IDCourse) VALUES ('Votre instrument', 'Comment chanter',2);

#affichage de la tab lessons
SELECT * FROM Lessons;

#affichage de la tab courses
SELECT * FROM Courses;
