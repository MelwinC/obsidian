--- 
# Problème

 ERR_PNPM_FETCH_404  GET http://artifactory.mgdis.fr/artifactory/api/npm/npm-repo/--no-install: Not Found - 404

This error happened while installing a direct dependency of /home/mcu/.cache/pnpm/dlx/qvtnvebcvpe7zvekblj2hhbcxy/19224a2ede9-7b08

--no-install is not in the npm registry, or you have no permission to fetch it.

No authorization header was set for the request.


---

# Solution

```
npx husky install // or pnpm or pnpm dlx
```


PS : C'est Yohann qui m'a passé cette solution, il a réussi à me débugguer somehow alors que ces commandes ont uniquement throw des erreurs (sauf une qui a juste rien fait) 🤡
Oui ce type est un génie, non il ne m'a pas payé, ni menacé pour écrire cela !