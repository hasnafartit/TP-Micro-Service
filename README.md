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
  on a definit une methode qui permet de retourner tous les comptes 
  et on a utiliser l'annotation '@GetMapping' qui contient une expression d’URL qui permet d'afficher tous les comptes
  
  ![image](https://user-images.githubusercontent.com/84719124/163491874-1c618cbb-0f56-4627-af89-ad7de33ce33b.png)

![image](https://user-images.githubusercontent.com/84719124/163491892-5900d601-f4fe-4c9e-a4d2-fb1043c9101c.png)


  puis on a ajouté une methode qui permer d'afficher un compte par son id
  
  ![image](https://user-images.githubusercontent.com/84719124/163491987-042fbc18-b816-436d-a679-d7fec9278794.png)


![image](https://user-images.githubusercontent.com/84719124/163492000-e2079c66-94c0-40d6-9f71-7b15b5bb2c10.png)


Puis on a ajouté une methode qui permet d'ajouter un compte (postMapping)

![image](https://user-images.githubusercontent.com/84719124/163511550-3e87f560-393c-4ce7-b485-b40f7680a3b6.png)



on a ajouté une methode qui permet de modifier un compte (PuMapping)

![image](https://user-images.githubusercontent.com/84719124/163511606-cabb7618-bd45-430a-8dc5-cbada7c0c30a.png)


n a ajouté une methode qui permet de supprimer un compte (DeleteMapping)


![image](https://user-images.githubusercontent.com/84719124/163511650-663e51db-4f1b-48de-aa15-82df11c31c60.png)


Puis on a utilisé postman pour tester le micro service:

afficher :

![image](https://user-images.githubusercontent.com/84719124/163512213-f957f7cf-99a3-4506-b268-5e2adecce227.png)

ajouter:

![image](https://user-images.githubusercontent.com/84719124/163512266-1a08ea7b-692f-4ebc-ac7f-99a0fd2066ec.png)

modifier:

![image](https://user-images.githubusercontent.com/84719124/163512309-af9ab524-f77c-4d5d-a9bc-81d7db1ea9c1.png)

![image](https://user-images.githubusercontent.com/84719124/163512401-4cae4f57-11c3-4454-a686-1e262060ba97.png)


supprimer :

![image](https://user-images.githubusercontent.com/84719124/163512431-fd5c9f19-68a2-43dd-a805-65186cda37cb.png)


![image](https://user-images.githubusercontent.com/84719124/163512450-2dee489a-aa9d-4b2a-abc0-8b9078c9da01.png)







