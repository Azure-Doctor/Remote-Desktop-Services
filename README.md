# 👋 Salut, moi c’est ton RDS Starter Kit

Tu veux déployer un environnement Remote Desktop Services (RDS) complet sur Azure **sans galérer** ?  
Ce repo est là pour toi 

---

##  L’objectif

T’aider à provisionner en quelques minutes une infra RDS fonctionnelle, claire, testable… sans passer ta nuit dans la doc Microsoft.

Avec ce kit, tu vas :

 Créer 6 machines virtuelles automatiquement  
 Monter ton propre domaine Active Directory (`A2i.local`)  
 Déployer les rôles RDS principaux (Broker, Web, Gateway, Session Hosts)  
Créer une collection `"A2i App Store"`  
 Publier deux RemoteApps de test (`cmd.exe` et `powershell.exe`)  
 Et tout ça, **en ligne de commande**, à ton rythme.

---

##  Ce que tu trouveras ici

 Un dossier `cli/` avec tous les scripts PowerShell prêts à l’emploi  
 Une structure claire, modulaire, que tu peux adapter à ton projet  
 Un schéma d’archi (si tu veux visualiser ce que tu installes)   Une convention de nommage standardisée :  
Toutes les ressources Azure commencent par : `a2i-webinar-demo-<truc>`  
Exemples :  
- `a2i-webinar-demo-rg001`  
- `a2i-webinar-demo-dc001`

---

##  Comment l’utiliser (promis, c’est pas sorcier)

```powershell
# 1. Connexion à Azure
az login
az account set --subscription "<ID de ton abonnement>"

# 2. Déploiement complet
.\cli\deploy-infra.ps1 -Location "westeurope" -Prefix "a2i-webinar-demo"

# 3. Intégration des VMs au domaine
.\cli\join-domain.ps1

# 4. Publication des RemoteApps
.\cli\publish-remoteapps.ps1 -CollectionName "A2i App Store"
🖼 À quoi ça ressemble ?
📷 Un schéma vaut mieux qu’un long discours :


 Pour qui c’est fait ?
Pour les pros qui en ont marre de :

 passer 3 heures à cliquer dans le portail
 chercher des tutos qui datent de 2016
 tomber sur 48 lignes d’erreurs PowerShell sans explication

Ici, tu suis les étapes, tu comprends ce que tu fais, tu as un résultat.

 Ce que tu peux faire après
Tu veux aller plus loin ?

Ajouter ton propre certificat ?

Remplacer les RemoteApps par une app métier ?

Intégrer ça dans un pipeline DevOps ?
➡️ Les bases sont là. Tu n’as plus qu’à adapter.

Licence
Ce projet est sous licence MIT. Tu peux l’utiliser, l’adapter, le partager.
(Si tu l’améliores, pense à la communauté )

Une question ? Une idée ?  
Les issues sont ouvertes, les pull requests sont bienvenues.
On est là pour apprendre ensemble, pas pour jouer au cowboy en solo 

RDS, c’est chiant quand c’est mal fait. Mais avec un bon starter kit, c’est fluide, propre et efficace.

Bon déploiement 🚀
