# Réparer 


## Voir un dossier 

Un dossier de réparation est toujours relatif à un [objet](how-it-works.md#objet). Pour voir un dossier, il est nécessaire de se rendre sur le [détail d'un objet](inventory.md#detail-d-un-objet). 

Un dossier se présente ainsi : 

![repair-folder](../assets/stuff/repair-folder.png)

Pour voir les interventions associées, il faut déplier l'accordéon en cliquant sur ***voir les interventions***. 

## Ajouter un dossier 

Pour ajouter un dossier, cliquer sur le bouton :fa-plus: qui suit ***Dossiers de réparations***

!!! info "qui peut créer un dossier ?"
    L'utilisateur propriétaire, les volontaires, actifs et administrateurs des organisations dont le propriétaire est membre. Si le propriétaire est une organisation, ces sont égalements ces membres-ci qui peuvent créer un dossier. 

![create-repair-folder](../assets/stuff/stuff-folder-create.png#small)

Ce formulaire reprend les champs décrivant un [dossier de réparation](how-it-works.md#dossier-de-reparation). 

Il faut indiquer une ```date d'ouverture``` et préciser si le dossier est en cours on non. 

Il est nécessaire de **renseigner ,à minima, une observation**. Cette observation consistera l'état innitial de l'objet lors de l'ouverture de ce dossier. 


## Ajouter/modifier une interventions

Pour ajouter une intervention à un dossier, cliquer sur le lien ***ajouter une intervention*** inclu dans un dossier de réparation.

Pour modifier une intervention, cliquer sur le bouton d'edition :fa-pencil: qui suit la ligne décivrant l'intervention. 

!!! info "qui peut ajouter/modifier ?"
    L'utilisateur propriétaire, les volontaires, actifs et administrateurs des organisations dont le propriétaire est membre. Si le propriétaire est une organisation, ces sont égalements ces membres-ci qui peuvent modifier/créer une intervention. 

![create-intervention](../assets/stuff/intervention.png#small)


Ce formulaire reprend les champs décrivant une [intervention](how-it-works.md#intervention). 

Outre la date de l'intervention et ses actions disponibles sous forme de champ d'autocomplétion, il est possible d'indiquer si cette intervention à eu un impact sur le dossier et son objet : 

* Si l'intervention clos le dossier. Le dossier passera donc du status **en cours** à **terminé**. 
* Si l'intervention modifie l'état général de l'objet. Une liste de choix d'état apparaît. L'état de l'objet sera ainsi modifié en conséquence. 