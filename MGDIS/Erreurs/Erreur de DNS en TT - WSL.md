S'il n'est pas possible de resolve le nom de domaine gitlab.mgdis.fr lors d'une commande git par exemple, cela est possiblement dû au DNS.

Pour vérifier si c'est bien le DNS, commencer par ping un nom de domaine public puis son IP en utilisant une connexion externe (partage de co par exemple) sans oublier d'activer son VPN.

(Depuis un terminal WSL)

```
ping google.com
```

```
ping 8.8.8.8 // ip de google.com
```

Si le ping n'atteint pas sa destination lors du premier ping mais que le second fonctionne, alors c'est en effet un problème de DNS.

Se diriger vers les fichiers de configuration dans un terminal WSL 
- `/etc/wsl.conf` et `/etc/resolv.conf`

Modifier le fichier wsl.conf pour qu'il ne regénère pas le resolv.conf au lancement du WSL

```
sudo nano /etc/wsl.conf
```
##### wsl.conf

```
[boot]  
systemd=true  
[network]  
generateResolvConf=false
```

Suite à cette modification, passer par cmd / powershell (terminaux windows) pour redémarrer WSL 

```
wsl --shutdown // stop le process
wsl // lance le process
```

Retourner sur un nouveau terminal WSL

Vérifier les changements apportés au fichier wsl.conf

```
cat /etc/wsl.conf
```

Modifier le fichier resolv.conf pour viser le bon serveur DNS

```
sudo nano /etc/resolv.conf
```
##### resolv.conf

```
nameserver 192.168.153.11
```


Une nouvelle fois redémarrer WSL 

```
wsl --shutdown // stop le process
wsl // lance le process
```

Et enfin vérifier que tout est correct, lire le fichier resolv.conf

```
cat /etc/resolv.conf
```

Ping à nouveau un nom de domaine 

```
ping google.com
ping gitlab.mgdis.fr
```