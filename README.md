# Guide de Déploiement Web : Choisir la Bonne Stratégie

Déployer une application web implique de choisir les meilleures options en fonction des caractéristiques de votre projet. Ce guide vous propose une vue d'ensemble des solutions de déploiement les plus adaptées selon le type de projet (statique, dynamique, type de framework, etc.).

## Table des Matières

1. [Applications Web Statique](#applications-web-statique)
2. [Applications Web Dynamiques](#applications-web-dynamiques)
3. [Framework PHP](#framework-php)
4. [Frameworks Frontend (React, Vue, Angular)](#frameworks-frontend-react-vue-angular)
5. [Applications Node.js](#applications-nodejs)
6. [Combinaison Frontend + Backend (JAMstack)](#combinaison-frontend--backend-jamstack)
7. [Résumé des Principales Plateformes](#résumé-des-principales-plateformes)
8. [Outils et Procédures de Base](#outils-et-procédures-de-base)

---

## Applications Web Statique

Les applications statiques contiennent des fichiers HTML, CSS et JS sans logique backend exécutée côté serveur. Voici les options de déploiement les plus populaires :

- **GitHub Pages** : Gratuit et facile d'utilisation, idéal pour des sites statiques ou de la documentation.
- **Netlify** : Automatisation du déploiement, CI/CD intégré, et supporte les fonctions serverless pour enrichir des sites statiques.
- **Vercel** : Adapté aux projets statiques et aux applications React/Next.js. Rapide et très facile à configurer.
- **AWS S3 + CloudFront** : Pour des besoins plus importants en scalabilité, Amazon S3 peut être utilisé avec CloudFront pour la distribution CDN.

### Cas d'utilisation
- **Portfolios**
- **Pages de documentation**
- **Sites vitrines**

## Applications Web Dynamiques

Les applications web dynamiques nécessitent une gestion des données côté serveur (bases de données, sessions utilisateur, etc.).

- **Heroku** : PaaS (Platform as a Service) qui prend en charge les langages populaires (Node.js, Python, Ruby, PHP). Facile à utiliser mais limité en scalabilité pour des projets à forte charge.
- **DigitalOcean App Platform** : Une alternative abordable, simple à utiliser et qui fournit des services managés pour des projets dynamiques.
- **AWS Elastic Beanstalk** : Permet de déployer des applications plus complexes. AWS EB offre une gestion simplifiée, mais nécessite quelques connaissances de base d'AWS.
- **Railway** : Une solution moderne qui simplifie le déploiement d'applications dynamiques avec une approche "plug-and-play".

### Cas d'utilisation
- **Sites e-commerce**
- **Applications nécessitant des interactions avec une base de données**
- **Applications de gestion**

## Framework PHP

Les projets utilisant un framework PHP comme Laravel, Symfony, ou même des CMS comme WordPress peuvent être déployés avec les options suivantes :

- **Shared Hosting (OVH, Bluehost, etc.)** : Souvent la solution la moins chère, recommandée pour des petits projets ou des sites WordPress.
- **VPS (DigitalOcean, Linode, Vultr)** : Pour un meilleur contrôle et des performances supérieures. Nécessite de configurer le serveur web (Apache/Nginx).
- **PaaS comme Heroku ou Platform.sh** : Fournit une approche simplifiée pour déployer des applications PHP sans gestion des serveurs.
- **Laravel Forge** : Outil spécifiquement conçu pour automatiser la configuration de serveurs et le déploiement des applications Laravel sur des services cloud (AWS, DigitalOcean).

### Cas d'utilisation
- **Sites WordPress**
- **Applications basées sur Laravel**

## Frameworks Frontend (React, Vue, Angular)

Pour des projets JavaScript modernes, généralement des Single Page Applications (SPA) :

- **Vercel** : Idéal pour les projets utilisant Next.js, mais fonctionne aussi avec d'autres frameworks (React, Vue).
- **Netlify** : Permet le déploiement continu et prend en charge les fonctions serverless pour les besoins backend légers.
- **Firebase Hosting** : Solution de Google qui fournit un hébergement rapide pour les applications SPA, avec des services intégrés comme l'authentification et la base de données.

### Cas d'utilisation
- **Applications client riches (dashboards)**
- **Sites nécessitant un rendu côté client rapide**

## Applications Node.js

Les applications backend Node.js ont besoin d'une gestion particulière pour les processus et les dépendances :

- **Heroku** : Supporte nativement Node.js et est facile à mettre en place.
- **Vercel** : Bien adapté aux applications utilisant Next.js, mais fonctionne aussi pour d'autres applications Node.js.
- **AWS Lambda + API Gateway** : Pour des applications serverless qui doivent scaler facilement. Prend en charge des fonctions Node.js sans serveur.
- **PM2 + VPS** : Une solution auto-gérée qui permet de gérer les processus et redémarrer les services en cas de crash. Nécessite des compétences d'administration serveur.

### Cas d'utilisation
- **API RESTful**
- **Services backend scalables**

## Combinaison Frontend + Backend (JAMstack)

Pour des projets combinant des parties frontend statiques et des services backend légers :

- **Netlify** : Déploiement des parties statiques, support des fonctions serverless pour un backend léger.
- **Vercel** : Idéal pour des projets Next.js, où le rendu est mixte (SSR/SSG).
- **AWS Amplify** : Permet d'héberger la partie frontend et d'utiliser des services serverless comme API Gateway ou Lambda pour la logique backend.

### Cas d'utilisation
- **Sites générés statiquement avec des fonctionnalités dynamiques**
- **Applications nécessitant des services authentification ou BDD sans serveur**

## Résumé des Principales Plateformes

| Type de Projet              | Plateformes Recommandées                |
|----------------------------|----------------------------------------|
| Site Statique              | GitHub Pages, Netlify, Vercel, AWS S3  |
| Application Dynamique      | Heroku, DigitalOcean, Railway, AWS EB  |
| Framework PHP              | Shared Hosting, VPS, Laravel Forge     |
| Frontend (React, Vue)      | Vercel, Netlify, Firebase Hosting      |
| Backend Node.js            | Heroku, AWS Lambda, PM2 + VPS          |
| JAMstack                   | Netlify, Vercel, AWS Amplify           |

## Outils et Procédures de Base

Lors du déploiement d'une application web, il est utile de connaître certains outils et procédures de base, notamment pour les options de déploiement les plus simples comme FTP et SSH.

### FTP (File Transfer Protocol)
FTP est l'un des moyens les plus basiques pour transférer des fichiers entre un ordinateur local et un serveur distant. C'est souvent utilisé pour des petits sites web ou des mises à jour ponctuelles.

- **Utilisation** : Les clients FTP comme FileZilla, Cyberduck ou WinSCP permettent de se connecter à un serveur web et de transférer des fichiers.
- **Avantages** : Simple à mettre en place et ne nécessite pas de compétences avancées.
- **Limites** : Pas idéal pour les projets complexes ou les déploiements automatisés. Moins sécurisé si utilisé sans SSL (FTPS).

### SSH (Secure Shell)
SSH est un protocole qui permet d'accéder à un serveur distant de manière sécurisée. Il est souvent utilisé pour gérer des serveurs, déployer des applications, et automatiser des tâches.

- **Utilisation** : SSH permet de se connecter directement à un serveur et d'exécuter des commandes. Les outils comme PuTTY (Windows) ou le terminal natif (Linux/macOS) sont couramment utilisés.
- **Scénarios courants** : Déployer des fichiers via SCP (Secure Copy Protocol), configurer des services, ou utiliser des outils comme Git pour cloner un dépôt directement sur le serveur.
- **Avantages** : Sécurisé et puissant. Permet d'automatiser des tâches grâce aux scripts bash.

### Rsync
**Rsync** est un outil de synchronisation de fichiers qui est souvent utilisé en complément de SSH pour déployer des fichiers de manière efficace.

- **Utilisation** : Transfère uniquement les modifications, ce qui le rend plus rapide que FTP pour les mises à jour.
- **Commande typique** : `rsync -avz ./local-folder/ user@server:/remote-folder/`
- **Avantages** : Très rapide et peut être automatisé facilement. Sécurisé lorsqu'il est utilisé avec SSH.

### Git et Déploiement via Git
Le déploiement via Git consiste à utiliser un dépôt Git pour transférer du code vers un serveur de production.

- **Git Hooks** : Les **hooks Git** peuvent être utilisés pour automatiser les actions après un `git push`, par exemple déployer une nouvelle version.
- **Plateformes** : De nombreuses plateformes de déploiement (comme Heroku, Netlify, Vercel) intègrent Git et permettent le déploiement continu à partir des dépôts GitHub, GitLab ou Bitbucket.
- **Avantages** : Idéal pour le déploiement continu et le travail en équipe. Permet de gérer le versionnage du code.

### SCP (Secure Copy)
**SCP** est une commande permettant de transférer des fichiers de manière sécurisée entre un ordinateur local et un serveur distant via SSH.

- **Utilisation** : `scp fichier.txt user@serveur:/chemin/remote`
- **Avantages** : Rapide et sécurisé. Très utile pour transférer quelques fichiers rapidement sans client FTP.
