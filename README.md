# 🖥️ RDS Starter Kit – PowerShell CLI

Ce dépôt contient un ensemble de scripts PowerShell pour déployer rapidement un environnement Remote Desktop Services (RDS) complet sur Microsoft Azure.  
Idéal pour les démos, les tests ou les formations techniques.

---

## 📌 Ce que ce kit installe

Le script `deploy-infra.ps1` vous permet de créer automatiquement les composants suivants :

- 1x Domain Controller (`A2i.local`)
- 2x RD Session Hosts
- 1x RD Connection Broker
- 1x RD Web Access
- 1x RD Gateway
- Création d’une collection nommée **A2i App Store**
- Publication des RemoteApps suivantes :
  - `cmd.exe`
  - `powershell.exe`

Toutes les VM sont jointes au domaine Active Directory déployé.

**Convention de nommage** :  
Toutes les ressources Azure commencent par `a2i-webinar-demo-`  
Exemples :  
- `a2i-webinar-demo-rg001`  
- `a2i-webinar-demo-dc001`  
- `a2i-webinar-demo-vnet001`

---

## 🧰 Prérequis

Avant de commencer, assurez-vous d’avoir :

- PowerShell 7 ou plus
- Azure CLI (v2.45 ou supérieur)
- Un abonnement Azure actif avec les droits `Contributeur`

---

## 🚀 Comment l’utiliser

Depuis PowerShell :

```powershell
# Connexion à Azure
az login
az account set --subscription "<ID de votre abonnement>"

# Déploiement de l’infrastructure
.\cli\deploy-infra.ps1 -Location "westeurope" -Prefix "a2i-webinar-demo"

# Joindre les VMs au domaine
.\cli\join-domain.ps1

# Publier les RemoteApps
.\cli\publish-remoteapps.ps1 -CollectionName "A2i App Store"
