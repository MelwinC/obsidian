1. M'attribuer le ticket correctif
2. Trouver d'où vient le bug
	1. Ouvrir l'écran sur l'env de dev 
	2. Trouver de quel endroit précis vient l'élément en erreur
	3. Inspecter l'élément pour récupérer son iframe 
	4. Aller sur le bon service correspondant à partir de la src de l'iframe (se mettre à jour du service)
	5. Trouver les fichiers concernés par l'élément
3. Analyse de dev
4. Créer une branche à partir de la branche dans laquelle le correctif doit être appliqué (alpha / beta, noté sur le ticket)
	1. Convention branche
		1. type/PLAID-XXXX-scope
		2. exemple : fix/PLAID-117716-
5. Dev le fix
6. TU
7. Commit / Push le fix
	1. Convention commit
		1. type(scope): description 
		2. exemple : fix(modele-piece): Send piece's fonction when deleting piece
8. Mettre à jour le service de l'env de dev
	- Exploitation
		- Mettre à jour un service
			1. service : service modifié (exemple : referentiel-piece)
			2. version à installer : branche qui vient d'être créée / push
9. Tester le fix sur l'env de dev
10. Si tout fonctionne -> MR
	1. Titre : message de commit (ou modifié si pas assez clair)
	2. Résumé : détail des modifs
	3. Assigné : moi
	4. Tag les personnes nécessaires à la MR (1 tech lead min) en fonction de leur scope (si une autre FT alors tag un tech-lead + ref front si concerné)
	5. Décocher squash commits (laisser cocher delete branch after MR)
11. Lorsque la MR est validée par les relecteurs -> Passage en relecture beta
	1. Changer d'assigné sur la MR gitlab, mettre Erwan Le Bideau
	2. Passer le ticket jira en relecture beta
		1. Mettre une description du correctif en ==français== 
		2. Indiquer le contexte du bug 
			-  Si effet de bord évolution / correctif indiquer le ticket en cause
		3. Me retirer du statut responsable sur le ticket jira


--- 

#### Pour squash les commits : 

```
git checkout <fix_branch_name>
git pull
git rebase -i HEAD~n (n: nb de commits) 
```

Laisser le "pick" sur le commit à conserver et remplacer les autres par 'f' (pour fixup) puis save le fichier

```
git push -f (après avoir vérifié les changements pour bien voir les commits supprimés VS le commit envoyé)
```
