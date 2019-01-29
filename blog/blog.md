# Description de la DataBase de Blog avec SQLITE3

## L'architecture de la base de donnée de l'app de blogging est la suivante :

### L'application va accueillir plusieurs user et ils auront tous un nom.

CREATE TABLE ‘user’ (
‘id’ INTEGER PRIMARY KEY AUTOINCREMENT, 
‘name’ TEXT
);


### Chaque utilisateur peut créer plusieurs article et chaque article est forcément créé par un user.

CREATE TABLE ‘article’ (
‘Id’ INTEGER PRIMARY KEY AUTOINCREMENT, 
‘name’ TEXT, 
user_id integer NOT NULL,
FOREIGN KEY (user_id) REFERENCES user(id));   

La relation entre la table article et user est de 1,n : un user pour un article. Dans ce cas, on doit integrer une foreign key dans la table qui a cette relation unique c-à-d la table article. 


### Un article peut appartenir à plusieurs category ; chaque category a un titre.

CREATE TABLE 'category' (
  'id' INTEGER PRIMARY KEY AUTOINCREMENT,
  'title' TEXT
  );

La relation entre la table article et la table category est de 'many to many' (n,n). Une category peut être associé à plusieurs articles et vice-versa. Dans ce cas là, on est obligé de faire une table intermediaire prenant en compte les deux clés primaires de ces tables. 

CREATE TABLE 'article_category' (
  'id_article' INTEGER,
  'id_category' INTEGER,
  FOREIGN KEY(id_article) REFERENCES article(articleId),
  FOREIGN KEY(id_category) REFERENCES category(id)
  );

### Une catégorie peut appartenir à plusieurs tag ; chaque tag a un titre et une couleur.

CREATE TABLE 'tag' (
   ...> 'id' INTEGER PRIMARY KEY AUTOINCREMENT,
   ...> 'title' TEXT,
   ...> 'color' TEXT);

La relation entre la table category et la table tag est de 'many to many' (n,n). Une category peut être associé à plusieurs tag et vice-versa. Dans ce cas là, on est obligé de faire une table intermediaire prenant en compte les deux clés primaires de ces tables. 

CREATE TABLE 'category_tag'(
  'id_category' INTEGER,
  'id_tag' INTEGER,
  FOREIGN KEY(id_category) REFERENCES category(id),
  FOREIGN KEY(id_tag) REFERENCES tag(id)
   );

## Voilà, explications données par Nora Bourouis, pour vous servir ;) 
