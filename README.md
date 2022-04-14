# TP-Micro-Service


Dans cette partie on a creé un simple micro-service(une application qui permet de gérer les comptes bancaire) avec spring boot.

Tout d'abord on a creer la classe compte où on a définit les attribut du compte bancaire et on a utilisé l'annotation '@Data' qui permet d'ajouter les getters et les setters , on a utilisé l'annotation '@NoArgsConstructor' qui permet de définir un constructeur sans parametre et aussi  on a utilisé l'annotation '@AllArgsConstructor' qui permet de définir un constructeur avec tous les parametres. Puis on a ajouté l'annotation '@Entity' pour que notre application soit une entités JPA
et ona ajouter les annotations 'Id' avant le code pour qu'il soit la clé primaire dans la table compte et @GenerateValue(strategy=....) pour avoir une ato incrementation.et pour l'annotation '@Enumerated(EnumType.String)' pour que le type de compte soit soit stocké au format string dans la base des données.



Ensuite on a creer l'interface CompteRepository qui été hirité de la classe JpaRespository.

Puis on a tester notre application par definir des comptes dans le main et on a les stocké dans la base de données comptedb on utilisant H2

voici l'exucution du 1er test de notre micro-service :

![image](https://user-images.githubusercontent.com/84719124/163490290-a220f2c1-a8c0-4495-824c-4d12fcb5f204.png)

Et pour voir ce qui est dans la base de données on a utilisé h2 console qui est une petit application web dans notre application qui permet d'acceder à la base de données

![image](https://user-images.githubusercontent.com/84719124/163490751-c6aceea7-02cf-400f-bdaf-19fea530c351.png)


![image](https://user-images.githubusercontent.com/84719124/163490781-c02af4c8-bae7-41b0-81a9-a87aef4a129f.png)


Après le test on a crée la classe CompteRestontroller :
  on a utilisé l'annotation '@RestController' pour creer un rest controller
  on a utilisé l'injection par le constructeur
  on a definit une methode qui permet de retourner tous les cpmptes 
  
