# holbertonschool-system_engineering-devops
### **Curriculum**
**[C#24] Foundations v2 - Part 3**  
**Moyenne : 49.65%**  
**Badge du projet : Conception d'infrastructure web**  
**Novice**  
**Par : Sylvain Kalache**  
**Poids : 1**  
**Une revue manuelle QA doit être effectuée (demandez-la lorsque vous avez terminé le projet)**

---

### **Description**
#### **Quiz**
Pour ce projet, nous attendons de vous que vous vous familiarisiez avec les concepts suivants :
- Bases du réseau
- Serveur
- Serveur web
- DNS
- Répartiteur de charge (Load balancer)
- Surveillance (Monitoring)

---

### **Ressources**
**Lire ou regarder :**
- [Page conceptuelle sur les bases du réseau](#)
- [Page conceptuelle sur les serveurs](#)
- [Page conceptuelle sur les serveurs web](#)
- [Page conceptuelle sur le DNS](#)
- [Page conceptuelle sur les répartiteurs de charge](#)
- [Page conceptuelle sur la surveillance](#)
- [Qu'est-ce qu'une base de données ?](#)
- [Quelle est la différence entre un serveur web et un serveur d'application ?](#)
- [Types d'enregistrements DNS](#)
- [Point de défaillance unique (Single Point of Failure)](#)
- [Comment éviter les temps d'arrêt lors du déploiement de nouveau code](#)
- [Cluster à haute disponibilité (actif-actif/actif-passif)](#)
- [Qu'est-ce que HTTPS ?](#)
- [Qu'est-ce qu'un pare-feu ?](#)

---

### **Objectifs d'apprentissage**
À la fin de ce projet, vous devez être capable d'expliquer à n'importe qui, sans l'aide de Google :

#### **Général**
- Vous devez être capable de dessiner un diagramme couvrant la pile web que vous avez construite avec les projets de la piste sysadmin/devops.
- Vous devez être capable d'expliquer ce que fait chaque composant.
- Vous devez être capable d'expliquer la redondance du système.
- Connaître tous les acronymes mentionnés : LAMP, SPOF, QPS.

---

### **Exigences**
#### **Général**
- Un fichier `README.md` à la racine du dossier du projet est obligatoire.
- Pour chaque tâche, une fois que vous avez terminé de dessiner (sur un tableau blanc, une feuille de papier ou un logiciel de votre choix), prenez une photo ou une capture d'écran de votre diagramme.
- Ce projet sera revu manuellement :
  - Lorsque chaque tâche est terminée, le nom de la tâche deviendra vert.
  - Téléversez une capture d'écran montrant que vous avez terminé les niveaux requis sur un service d'hébergement d'images (j'utilise personnellement Imgur, mais vous pouvez utiliser ce que vous voulez).
  - Pour les tâches suivantes, insérez le lien de votre capture d'écran dans le fichier de réponses.
  - Après avoir poussé votre fichier de réponses sur GitHub, insérez le lien du fichier GitHub dans la boîte URL.
- Vous devrez également dessiner chaque tâche sur un tableau blanc devant un mentor, un membre du personnel ou un étudiant - aucun ordinateur ou note ne sera autorisé pendant la session de dessin.
- Concentrez-vous sur ce qui vous est demandé :
  - Couvrez ce que les exigences mentionnent, nous explorerons les détails dans un projet ultérieur.
  - Gardez à l'esprit que vous aurez 30 minutes pour effectuer l'exercice, vous obtiendrez des points pour ce qui est demandé dans les exigences.
  - De même, lors d'un entretien d'embauche, vous devez répondre à ce que l'interviewer demande, faites attention à ne pas être trop verbeux - demandez toujours à l'interviewer si entrer dans les détails est nécessaire - parler trop peut jouer contre vous.
  - Dans ce projet, encore une fois, évitez d'entrer dans les détails si ce n'est pas demandé.

---

### **Tâches**

#### **0. Infrastructure web simple**
**Obligatoire**  
Beaucoup de sites web sont alimentés par une infrastructure web simple, souvent composée d'un seul serveur avec une pile LAMP.

Sur un tableau blanc, concevez une infrastructure web à un serveur qui héberge le site web accessible via `www.foobar.com`. Commencez votre explication en ayant un utilisateur qui souhaite accéder à votre site web.

**Exigences :**
- Vous devez utiliser :
  - 1 serveur
  - 1 serveur web (Nginx)
  - 1 serveur d'application
  - 1 ensemble de fichiers d'application (votre base de code)
  - 1 base de données (MySQL)
  - 1 nom de domaine `foobar.com` configuré avec un enregistrement `www` qui pointe vers l'IP de votre serveur `8.8.8.8`
- Vous devez être capable d'expliquer certains détails sur cette infrastructure :
  - Qu'est-ce qu'un serveur ?
  - Quel est le rôle du nom de domaine ?
  - Quel type d'enregistrement DNS est `www` dans `www.foobar.com` ?
  - Quel est le rôle du serveur web ?
  - Quel est le rôle du serveur d'application ?
  - Quel est le rôle de la base de données ?
  - Qu'est-ce que le serveur utilise pour communiquer avec l'ordinateur de l'utilisateur demandant le site web ?
- Vous devez être capable d'expliquer les problèmes de cette infrastructure :
  - Point de défaillance unique (SPOF)
  - Temps d'arrêt lors de la maintenance (comme le déploiement de nouveau code, le serveur web doit être redémarré)
  - Impossible de monter en charge en cas de trop de trafic entrant

**Dépôt :**
- Dépôt GitHub : `holbertonschool-system_engineering-devops`
- Répertoire : `web_infrastructure_design`
- Fichier : `0-simple_web_stack`

---

#### **1. Infrastructure web distribuée**
**Obligatoire**  
Sur un tableau blanc, concevez une infrastructure web à trois serveurs qui héberge le site web `www.foobar.com`.

**Exigences :**
- Vous devez ajouter :
  - 2 serveurs supplémentaires
  - 1 serveur web (Nginx)
  - 1 serveur d'application
  - 1 répartiteur de charge (HAproxy)
  - 1 ensemble de fichiers d'application (votre base de code)
  - 1 base de données (MySQL)
- Vous devez être capable d'expliquer certains détails sur cette infrastructure :
  - Pour chaque élément supplémentaire, pourquoi vous l'ajoutez
  - Quel algorithme de distribution votre répartiteur de charge est configuré et comment il fonctionne
  - Votre répartiteur de charge est-il configuré en mode actif-actif ou actif-passif, expliquez la différence entre les deux
  - Comment fonctionne un cluster de base de données Primary-Replica (Master-Slave)
  - Quelle est la différence entre le nœud Primary et le nœud Replica en ce qui concerne l'application
- Vous devez être capable d'expliquer les problèmes de cette infrastructure :
  - Où sont les points de défaillance unique (SPOF)
  - Problèmes de sécurité (pas de pare-feu, pas de HTTPS)
  - Pas de surveillance

**Dépôt :**
- Dépôt GitHub : `holbertonschool-system_engineering-devops`
- Répertoire : `web_infrastructure_design`
- Fichier : `1-distributed_web_infrastructure`

---

#### **2. Infrastructure web sécurisée et surveillée**
**Obligatoire**  
Sur un tableau blanc, concevez une infrastructure web à trois serveurs qui héberge le site web `www.foobar.com`. Elle doit être sécurisée, servir du trafic chiffré et être surveillée.

**Exigences :**
- Vous devez ajouter :
  - 3 pare-feux
  - 1 certificat SSL pour servir `www.foobar.com` via HTTPS
  - 3 clients de surveillance (collecteur de données pour Sumologic ou d'autres services de surveillance)
- Vous devez être capable d'expliquer certains détails sur cette infrastructure :
  - Pour chaque élément supplémentaire, pourquoi vous l'ajoutez
  - À quoi servent les pare-feux
  - Pourquoi le trafic est servi via HTTPS
  - À quoi sert la surveillance
  - Comment l'outil de surveillance collecte les données
  - Expliquez ce qu'il faut faire si vous voulez surveiller le QPS de votre serveur web
- Vous devez être capable d'expliquer les problèmes de cette infrastructure :
  - Pourquoi terminer SSL au niveau du répartiteur de charge est un problème
  - Pourquoi avoir un seul serveur MySQL capable d'accepter des écritures est un problème
  - Pourquoi avoir des serveurs avec tous les mêmes composants (base de données, serveur web et serveur d'application) peut être un problème

**Dépôt :**
- Dépôt GitHub : `holbertonschool-system_engineering-devops`
- Répertoire : `web_infrastructure_design`
- Fichier : `2-secured_and_monitored_web_infrastructure`

---

#### **3. Montée en charge**
**Obligatoire**  
**Readme**

**Serveur d'application vs serveur web**

**Exigences :**
- Vous devez ajouter :
  - 1 serveur supplémentaire
  - 1 répartiteur de charge (HAproxy) configuré en cluster avec l'autre
  - Séparer les composants (serveur web, serveur d'application, base de données) sur leurs propres serveurs
- Vous devez être capable d'expliquer certains détails sur cette infrastructure :
  - Pour chaque élément supplémentaire, pourquoi vous l'ajoutez

**Dépôt :**
- Dépôt GitHub : `holbertonschool-system_engineering-devops`
- Répertoire : `web_infrastructure_design`
- Fichier : `3-scale_up`

---

### **Synthèse des exercices**

#### **0. Infrastructure web simple**
- **Objectif** : Concevoir une infrastructure web basique avec un seul serveur.
- **À faire** :
  - Dessiner un diagramme montrant un serveur unique avec Nginx, une base de données MySQL, et un serveur d'application.
  - Expliquer le rôle de chaque composant et les problèmes potentiels (SPOF, temps d'arrêt, etc.).

#### **1. Infrastructure web distribuée**
- **Objectif** : Concevoir une infrastructure web distribuée avec trois serveurs.
- **À faire** :
  - Ajouter un répartiteur de charge (HAproxy) et expliquer son rôle.
  - Expliquer la différence entre les modes actif-actif et actif-passif.
  - Identifier les points de défaillance unique et les problèmes de sécurité.

#### **2. Infrastructure web sécurisée et surveillée**
- **Objectif** : Ajouter des pare-feux, HTTPS et des outils de surveillance à l'infrastructure.
- **À faire** :
  - Expliquer l'importance des pare-feux, de HTTPS et de la surveillance.
  - Identifier les problèmes liés à la terminaison SSL et à la redondance de la base de données.

#### **3. Montée en charge**
- **Objectif** : Ajouter un serveur supplémentaire et séparer les composants pour améliorer la scalabilité.
- **À faire** :
  - Expliquer pourquoi chaque composant est ajouté et comment cela améliore la performance et la redondance.

---
