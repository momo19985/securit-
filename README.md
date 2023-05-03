# securit-




J’'illustre la préparation d'un environnement de travail pour l'utilisation du protocole d'authentification Kerberos. Puis, l'installation de l'outil et la prise en main de cet outil. Je présente comment créer un administrateur de la base données de Kerberos, la création d'un principal et l'octroi d'un ticket. Et les notions de base la table de clés Keytab.



# Authentification-with-Kerberos

A brief description of what this project does and who it's for

Dans note cadre du projet nous avons utilisé deux machines virtuelles

Pour utiliser Kerberos nous avons deux contrainte, premièrement nous devons construire une DNS et
avoir une synchronisation d’horloge


## Synchronisation d’horloge

#### Machine 1: Serveur

#### output
![capture1](https://user-images.githubusercontent.com/74620773/236061454-0d0bd3c7-5df2-40c6-840f-572460e7c906.png)



#### Machine 2: Client
![capture1](https://user-images.githubusercontent.com/74620773/236060193-78ef15b5-d106-4684-a6ac-6ed18af79c2a.png)

#### output
## Configuration du DNS

#### Machine 1

#### output
![2](https://user-images.githubusercontent.com/74620773/236061704-8693c23b-728b-484d-9281-d6afe5698d6b.png)
![3](https://user-images.githubusercontent.com/74620773/236061925-51010fc6-0458-44b9-b88e-438e3579f833.png)

#### Machine 2

#### output
![2](https://user-images.githubusercontent.com/74620773/236062023-5dbb5da6-e08c-4ba9-9ada-a2fb6fb5774a.png)
![3](https://user-images.githubusercontent.com/74620773/236062052-1363d7f0-dc79-43b0-a2c4-c804fd63ed7a.png)


### Verification de connexion

ici nous avons vérifié si les 2 machines se sont connecté entre elle

#### Machine 1

#### output
![4](https://user-images.githubusercontent.com/74620773/236062183-1c7fee2e-57f0-4616-96c4-e88253e825c1.png)
![5](https://user-images.githubusercontent.com/74620773/236062247-b914cba9-8dc3-4d1d-9273-db8162ad5e23.png)

#### output


#### Machine 2
output
![5](https://user-images.githubusercontent.com/74620773/236062366-9c05c5a0-f491-4ca9-a6d9-1c4b30e959fb.png)


Une fois que nous avons vu que tout marche  et que notre environnement du travail a été préparer, nous somme enfin prêt pour l’installation de Kerberos et utiliser ces services

## Installation de Kerberos

#### Output
![6](https://user-images.githubusercontent.com/74620773/236062452-082d7c0f-3c4d-4c50-a8a9-e3c1192661c3.png)


Dans les captures d’ecran ci-dessous c’est la premiere interface qui apparait lors de installation :c’est la configuration de keberos authentification


#### Output![7](https://user-images.githubusercontent.com/74620773/236062898-d51fb3b2-5f8a-489a-a3ee-4ddbcc5d2629.png)

![8](https://user-images.githubusercontent.com/74620773/236063025-8a8d3d61-ec89-4b95-b208-a844b9c67869.png)

![9](https://user-images.githubusercontent.com/74620773/236063346-9ec557a9-b55f-4107-bff2-3adc8f64734b.png)

#### Output
#### Output

Une fois que nous avons terminé l’installation, nous allons jeter un coup-œil au niveau des fichiers de configurations
Ici nous avons  les éléments qu’on a configurer lors de l’installations de Kerberos qui est en quelque sort le moteur ou le noyau

#### Output
![10](https://user-images.githubusercontent.com/74620773/236063428-112d669e-18a1-486f-a148-0bbb30affd93.png)

#### Output
![11](https://user-images.githubusercontent.com/74620773/236063480-8b17935c-1394-4613-9080-5fa912e96906.png)

Apres l’installation, on va attribué un mot de passe pour le noyau avec la commande suivante :
#### Output
![12](https://user-images.githubusercontent.com/74620773/236063533-a5092e67-acca-4c46-8bd1-f96052953610.png)

Verification
#### Output
![13](https://user-images.githubusercontent.com/74620773/236063645-9a4577a8-8570-4572-8b21-ae868363fe97.png)

Par la suite on va accéder au fichier kadm5.acl afin de pourvoir ajouter quelques modifications
#### Output
![14](https://user-images.githubusercontent.com/74620773/236063733-f73253b6-ffc5-4a9a-bc7d-e00158ea67a4.png)

Ensuite on va créer des principaux
#### Output
![15](https://user-images.githubusercontent.com/74620773/236063798-eb79a9bc-58a5-4942-95c4-6be449f8efee.png)

Créer un utilisateur user :
#### Output
![16](https://user-images.githubusercontent.com/74620773/236063847-f4555737-f3d7-43fa-be74-24703f5c6ca2.png)

Afficher user qu’on vient de créer 
#### Output
![17](https://user-images.githubusercontent.com/74620773/236063915-9e7049ff-6c21-40b9-8c07-014be4da06ac.png)

Voir les information du user :
#### Output
![18](https://user-images.githubusercontent.com/74620773/236063965-140c2a98-eb2b-408a-9b28-b87c405e0416.png)

Créer un ticket pour le service qui est l’angle host et on va le tester :
#### Output
![19](https://user-images.githubusercontent.com/74620773/236064023-692ca19f-9745-4cbc-8e13-dd3ca460f36b.png)

Un aperçu pour voir comment on crée un ticket :
#### Output
![20](https://user-images.githubusercontent.com/74620773/236064071-470dc3ee-3d7c-42b0-9d4c-2abdc7d6589d.png)

Créer un host pour pouvoir ensuite l’authentifier ce service :
#### Output
![21](https://user-images.githubusercontent.com/74620773/236064205-36d94d6b-2520-442f-9622-16f98c20fb10.png)

Demarage des systèmes kerberos
#### Output
![22](https://user-images.githubusercontent.com/74620773/236064248-b894ea9e-1d02-45cd-ba76-57c088a61ca6.png)

Apres on va passer a la creation de keytab et ajouter un algorithme de chiffrement :
#### Output
![23](https://user-images.githubusercontent.com/74620773/236064302-9c2102ce-f20e-418b-abee-53918fde217e.png)

Verification du fichier kadm5.keytab
#### Output
![24](https://user-images.githubusercontent.com/74620773/236064392-95c2b888-4cd8-4bff-bf38-f9d59b375642.png)

#### Output
![25](https://user-images.githubusercontent.com/74620773/236064449-186b96af-dfde-4f25-8a37-c12f08ba3e46.png)

Une autre manière de créer un host :
#### Output
![26](https://user-images.githubusercontent.com/74620773/236064507-5c5b79d6-8c7d-4b89-8beb-bdc2cb6ea711.png)
