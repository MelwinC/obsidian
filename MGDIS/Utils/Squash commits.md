```
git checkout <fix_branch_name>
git pull
git rebase -i HEAD~n (n: nb de commits) 
```

Laisser le "pick" sur le commit à conserver et remplacer les autres par 'f' (pour fixup) puis save le fichier

Avant de push, vérifier les changements pour bien voir les commits supprimés VS le commit envoyé

```
git push -f (pas sync changes ça ne fonctionne pas)
```
