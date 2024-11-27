## Jira - MR

Lorsqu'il y a un patch d'indiqué sur le ticket Jira :

![[Pasted image 20241127092330.png]]

Lors du passage en MR vérifier si le ticket pour le patch a été créé 

![[Pasted image 20241127092503.png]]

Sinon, créer le patch pour la MR ici : 

![[Pasted image 20241127092427.png]]


## Branches patch PA-TNR

Maintenant que le patch est créé sur Jira il faut créer des MR pour chaque version jusqu'à la version indiquée sur le ticket (en remontant à partir de la beta).

Pour voir les branches hotfix qui correspondent à la version à patcher il faut aller se referrer à l'outil d'aide aux reports de patch de pa-tnr.

![[Pasted image 20241127094015.png]]

![[Pasted image 20241127094530.png]]

Ici dans mon exemple je devais patcher jusqu'à 250, donc je vais devoir faire des MR sur les hotfix 1.15.0 et 1.14.2.
Si la branche hotfix pour la version n'existe pas encore, alors il faut la créer. 

## Git

Maintenant il faudra faire une MR pour chaque version (je reprend l'exemple):
- D'abord faire la MR classique en créant une branche à partir de la beta
- Hotfix 1.14.2
	- Faire une branche à partir de la hotfix (même nom de branche que la beta, ajouter -1-14 à la fin)
	- Faire un / des cherry-pick du / des commit(s) appliqué(s) sur la beta
		- git cherry-pick <reference_du_commit>(ici 1e3851db)![[Pasted image 20241127094959.png]]
	- Push sur la branche hotfix 
	- Créer la MR pour la hotfix, préciser dans le title de la MR le numéro de hotfix : ![[Pasted image 20241127095947.png]]
	- Ajouter le numéro de PLAID du patch créé
	   ![[Pasted image 20241127100013.png]]
- Même chose pour l'autre branche hotfix

==/!\ Important /!\ ==
Sur la MR beta, lorsque la MR a été validée, assigner Erwan LE BIDEAU comme d'habitude, par contre sur les hotfix, assigner Fabrice MARQUES.
Si la MR sur la beta a été validée et que le modifs sont exactement les mêmes sur les hotfix, pas besoin l'approbation sur les autres MR.

## Jira - Relecture beta

Dans le cadre d'un patch, la PublicZone est nécessaire, au lieu de passer directement en RB, il faut donc modifier que le descriptif du ticket d'abord : 
- Modifier -> Documentations -> Descriptif (mettre le descriptif en français)

Ensuite il faut faire appel au PO qui a visé le ticket pour qu'il saisisse la PublicZone.
Quand c'est fait, on peut passer en RB.