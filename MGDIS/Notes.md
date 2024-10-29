
Préparer la grille d'évaluation pour le 19/11/24 (passer sous excel)
Réfléchir aux missions faites en entreprise (segmenter)
### Questions

1. 

--- 

### WIP

[PLAID-112791](https://jira.mgdis.fr/browse/PLAID-112791)
- État actuel : 
	1. erreur console sur mg-badge -> value dans doc collect
		- Erreur value prop sur les mg-badge
			- Valeur envoyée : length du tableau piece.documents (valeur === 0)
			- Attendu : integer / string / "?" / "!" / "*"
			- Erreur comme si la valeur envoyée ne match pas la condition, à voir si la valeur ne match pas que lors de l'initialisation de la page et ensuite la valeur attribuée match
	2. Autre erreur console sur les balises link vers les fichiers css dans data-schemas. Probablement à ne pas supprimer car possiblement présent dans d'autres tenants / env

[PLAID-116931](https://jira.mgdis.fr/browse/PLAID-116931)
- Ticket migration uic -> mg-comp composant datepicker avec Martin & Alexandre, analyse à lancer lors de la semaine de mon retour le 14 

[PLAID-117716](https://jira.mgdis.fr/browse/PLAID-117716)
	Erreur infos comp
	Champ obligatoire avec une règle de validation non respectée peut-être enregistrée
	Partir de l'epic de Yohann pour appliquer le dev ([https://jira.mgdis.fr/browse/PLAID-105171](https://jira.mgdis.fr/browse/PLAID-105171 "https://jira.mgdis.fr/browse/plaid-105171")
Se connecter - MGDIS JIRA) ou de l'alpha si c'est merged à mon retour
	TU pour le champ numeric-type

TODO 
Continuer 117716 (voir au dessus)
- TU WIP - Modifier le TU pour avoir les 3 cas : 
	- valeur qui respecte la règle de validation
	- valeur qui ne respecte pas la règle de validation
	- valeur null
- Faire des snapshots pour ces 3 cas en plus de checker fieldValidity & errorMessage en fonction de la modif qu'on a apporté
- Partir de la branche alpha ou de l'epic pour appliquer le dev
Continuer 112791 (voir au dessus)
- Voir pour l'erreur value prop sur le mg-badge, quand on envoie manuellement une valeur de type number (0) ce n'est pas valide, si l'on envoie une string ("0") c'est valide. 
- La regex indique pourtant qu'elle accepte les number et les string