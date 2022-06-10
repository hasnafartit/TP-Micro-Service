# TP-Micro-Service


Dans cette partie on a creé un simple micro-service(une application qui permet de gérer les comptes bancaire) avec spring boot.

Tout d'abord on a creer la classe compte où on a définit les attribut du compte bancaire et on a utilisé l'annotation '@Data' qui permet d'ajouter les getters et les setters , on a utilisé l'annotation '@NoArgsConstructor' qui permet de définir un constructeur sans parametre et aussi  on a utilisé l'annotation '@AllArgsConstructor' qui permet de définir un constructeur avec tous les parametres. Puis on a ajouté l'annotation '@Entity' pour que notre application soit une entités JPA
et ona ajouter les annotations '@Id' avant le code pour qu'il soit la clé primaire dans la table compte et @GenerateValue(strategy=....) pour avoir une ato incrementation.et pour l'annotation '@Enumerated(EnumType.String)' pour que le type de compte soit soit stocké au format string dans la base des données.



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



puis on a vu la DOCUMENTATION API qui donne des informations sur le micro service

![image](https://user-images.githubusercontent.com/84719124/163512624-671b71ed-0bd4-4ae9-8167-40b26f50871f.png)


puis on a importer la documentation API dans postman :
  ceci facilte le travail puisque on peut afficher,modifier... en cliquant sur get,put ...
  voici des exemples:
  AFFICHER tous les comptes : 
  ![image](https://user-images.githubusercontent.com/84719124/163513105-ed60f21d-8b0a-4a43-997c-4c2175b75fc9.png)
  Afficher un seul compte par leur id :
  
  ![image](https://user-images.githubusercontent.com/84719124/163513208-21117023-c12e-437b-abc9-9f83bc33d7ba.png)

  
  Inserer:
  
  ![image](https://user-images.githubusercontent.com/84719124/163513122-da7702f7-190a-43e6-a37c-f51e8a830023.png)



Modifier :

![image](https://user-images.githubusercontent.com/84719124/163513240-2f9b5d27-c3ad-422b-ad95-a89ea2f0e55c.png)

Supprimer :

![image](https://user-images.githubusercontent.com/84719124/163513353-385f9784-108c-4d39-991a-14e3fcef86cf.png)


Il y a une atre methode pour tester le micro-service et cela par l'utilisation de swagger :

tester get (afficher):

![image](https://user-images.githubusercontent.com/84719124/163514534-cde9b356-01b0-4a68-8975-f744f821a15b.png)


Inserer :
![image](https://user-images.githubusercontent.com/84719124/163514567-c973a95b-1c3a-4a5f-801b-e61acae16b29.png)

![image](https://user-images.githubusercontent.com/84719124/163514586-15bead90-2620-42e7-824b-f2f0b2a8af0e.png)


afficher un compte par son id :

![image](https://user-images.githubusercontent.com/84719124/163514626-8331cd91-491f-4642-a874-e924945aed44.png)


Supprimer :

![image](https://user-images.githubusercontent.com/84719124/163514681-f283ff1e-c5ea-4fb1-94a2-6e7189dc191e.png)


SPRING DATA REST
Apres on a supprimer l'annotation '@RestController' qui est donc la classe CompteRestController et on a ajouter l'annotation '@Respositoryestesource'(qui appartient spring data rest) dans la classe CompteRespository qui donne un web service et qui demare un Rest conntroller qui permet d'acceder à tous les methode qui ont dans cette interface 

Le test de ce qu'on a fait:

![image](https://user-images.githubusercontent.com/84719124/163565487-4494fa5f-69e0-4d94-978f-a431bc2fe66f.png)


visité la page 0(c à d la 1ere page) et afficher 2 comptes :
![image](https://user-images.githubusercontent.com/84719124/163565773-0c3c0cc4-539c-43fc-88ad-77f9db6635ed.png)

visité la page 1(c à d la 2eme page) et afficher 2 comptes :

![image](https://user-images.githubusercontent.com/84719124/163565942-b8596c45-873c-46cf-802e-009c1fe07434.png)


Apres ona crer une interface pour faire la projection (qu'il offre spring data rest) on a utilisé l'annotation '@Projection'

![image](https://user-images.githubusercontent.com/84719124/163566216-f9548732-2491-46f3-9cf0-05a242cb22f0.png)
ici ona crée une projection qui s'appelle p1 qui permet d'afficher le code et le solde

tester la projection p1 :

![image](https://user-images.githubusercontent.com/84719124/163566305-58241718-274b-4efa-b582-2303decafeff.png)

puis on a crer une projection 2 qui permet d'afficher le solde et le type:

![image](https://user-images.githubusercontent.com/84719124/163566459-29465f6f-44f9-4822-b498-3ab07aea3b06.png)

tester la projection 2:

![image](https://user-images.githubusercontent.com/84719124/163566584-ae85c0ea-2f07-4aae-b86a-36f9cfabb281.png)


puis on a ajouter dans la classe principal un rest configuration pour exposer le id :

![image](https://user-images.githubusercontent.com/84719124/163567060-aa7c96b9-e5f7-4c47-80b2-76717b6ba621.png)

test:

afichage avant la configuration :
![image](https://user-images.githubusercontent.com/84719124/163567159-ec3d1a6d-eccb-48a9-a2ba-b39ab7ce1b7f.png)

afichage apres l'ajout de la configuration :

![image](https://user-images.githubusercontent.com/84719124/163567215-10e347bc-64e8-4990-adfc-01690df7687f.png)


Puis on a ajouter une methode findByType pour qu'on puisse acceder a un compte par le type

![image](https://user-images.githubusercontent.com/84719124/163567415-afc4749c-485d-4088-9cbe-82a7d3380bce.png)

test:

type courant :
![image](https://user-images.githubusercontent.com/84719124/163567433-99cd4a30-de4e-43cc-96d8-2043f45799cd.png)


type epargne :
![image](https://user-images.githubusercontent.com/84719124/163567486-c57abb2a-4074-494a-abc8-884070a798fe.png)


Ensuite on a creer l'interface Compte service pour definir une methode virement on a utilise l'annotation '@Service' pour qu'il soit une composante de la couche servivce 
puis on a ajouter l'annotation '@Transactional' pour que les methodes seront transactionnel

Apres on a Creer un autre rest controller pour tester la methode virement et on a creé unz classe DTO pour definir les parametre dont on a besoin pour faire un virement : 

voici le rest controller :
![image](https://user-images.githubusercontent.com/84719124/163568310-b9bdf065-0a70-426c-bd02-0253cce1d354.png)

voici le test :

  les comptes avant le virement :
  ![image](https://user-images.githubusercontent.com/84719124/163568350-1f31fc4d-05bd-454a-87ee-11c7a1847281.png)
  
  le virement :
  
  ![image](https://user-images.githubusercontent.com/84719124/163568396-5568861c-9fe2-4df6-9abe-18ee8bf337a5.png)

  les comptesapres le virement :

![image](https://user-images.githubusercontent.com/84719124/163568464-20ac5169-dc99-4dec-9af6-6fe24fb2038b.png)

