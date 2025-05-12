--------------------------------------------------------------------------------------------------------------------------------

					# Collection de Maillots de Football  

Ce projet présente une application de gestion des collections de maillots de football contenus dans les vestiaires de différents supporters. Chaque maillot est associé à des informations détaillées telles que :  
- Le nom du joueur.  
- Le club auquel il appartient.  
- Le numéro du maillot.  

**Remarque** : Les clubs des joueurs peuvent évoluer au fil du temps. Par exemple, un maillot de Cristiano Ronaldo peut être associé à Manchester United, même si ce dernier joue actuellement pour Al-Nassr.  

--------------------------------------------------------------------------------------------------------------------------------
Première utilisation du prpojet : 


cd MonJerseys/

Testez que composer peut télécharger toutes les dépendances et que l'application Symfony se lance :

rm -fr composer.lock symfony.lock vendor/ var/cache/
symfony composer install
symfony server:start

					## Accès au projet  

Pour accéder à l'application et découvrir ses fonctionnalités, rendez-vous sur :  
http://localhost:8000/login  

--------------------------------------------------------------------------------------------------------------------------------

					### Comptes de test  

- **Compte administrateur** :  
  - Identifiant : `belkacem@localhost`  
  - Mot de passe : `123456`  

- **Compte utilisateur normal** :  
  - Identifiant : `olivier@localhost`  
  - Mot de passe : `123456`  

-**Compte visiteur** : 
 -Dans la barre de menu 

--------------------------------------------------------------------------------------------------------------------------------

					### Règles d'accès  


- Un **membre** peut :  
  - Modifier uniquement sa propre fiche utilisateur.  
  - Voir uniquement ses vestiaires non publiés dans l'onglet "Liste des Vestiaires" ainsi que dans sa fiche personnelle. Ajouter    un vestiaire non public pour le constater.  

- L'**administrateur** :  
  - A accès à toutes les informations et peut tout modifier sans restriction.  

-Visiteur : 
 -Peut simplement faire de la consultation partout. Cliquer sur "membre" dans la page d'accueil. 



					### Recommandation  

Pour apprécier les fonctionnalités évoquées, utilisez les comptes de test mentionnés ci-dessus.  

--------------------------------------------------------------------------------------------------------------------------------
					## Nomenclature utilisée  

- **[objet]** : Maillot de Football  
- **[inventaire]** : Armoire  
- **[galerie]** : Vestiaire  
- **[créateur]** : Supporter  

--------------------------------------------------------------------------------------------------------------------------------

				## Définition des propriétés à gérer  

### **Entité : Armoire (Inventaire)**  
| Nom de propriété | Type    | Contraintes  |  
|-------------------|---------|--------------|  
| Description       | String  | NotNull      |  
| Propriétaire      | String  | NotNull      |  

### **Entité : Maillot (Objet)**  
| Nom de propriété | Type    | Contraintes  |  
|-------------------|---------|--------------|  
| Description       | String  | NotNull      |  
| Club              | String  | NotNull      |  
| Joueur            | String  | NotNull      |  
| Numéro            | Int     | NotNull      |  

### **Entité : Vestiaire (Galerie)**  
| Nom de propriété | Type    | Contraintes  |  
|-------------------|---------|--------------|  
| Description       | String  | NotNull      |  
| Publiee          | Boolean | NotNull      |  
| Supporter_id      | Int     | NotNull      |  

### **Entité : Member (User)**  
| Nom de propriété | Type    | Contraintes  |  
|-------------------|---------|--------------|  
| Email            | String  | NotNull      |  
| Password         | String  | NotNull      |  
| Armoire_id       | String  | NotNull      |  
| ROLE             | String  | NotNull      |  

--------------------------------------------------------------------------------------------------------------------------------

## Relations entre entités  

- **One-To-Many** entre `Armoire` et `Maillot`.  
- **One-To-Many** entre `Member` et `Vestiaire`.  
- **Many-To-Many** entre `Maillot` et `Vestiaire`.  
- **One-To-One** entre `Member` et `Armoire`.  

---------------------------------------------------------------------------------------------------------------------------------


## Informations supplémentaires  

L'application utilise Symfony, PHP, Twig, CSS, et HTML pour créer un site performant et intuitif, adapté à la gestion des collections personnelles et partagées.  

--------------------------------------------------------------------------------------------------------------------------------
  
