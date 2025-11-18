# Devis - Plugin WordPress sur mesure "Espace Client Mon Plant Fraise"

**Date :** 18 novembre 2025
**Projet :** Développement d'un plugin WordPress personnalisé pour plateforme de crowdfunding agricole
**Client :** MPF Group
**Validité :** 30 jours

---

## 1. CONTEXTE DU PROJET

Développement d'un plugin WordPress sur mesure reproduisant toutes les fonctionnalités de l'espace client actuel de Mon Plant Fraise, une plateforme de financement participatif agricole pour le parrainage de plants de fraisiers.

Le plugin permettra aux utilisateurs de gérer leurs investissements, suivre leurs rendements, parrainer d'autres membres, et commander des produits, le tout dans un environnement WordPress sécurisé et moderne.

---

## 2. PÉRIMÈTRE FONCTIONNEL

### 2.1 Authentification et Gestion de Compte

#### Inscription des Membres
- Formulaire d'inscription personnalisé avec validation avancée
- Validation par email (double opt-in)
- Génération automatique du code parrain unique
- Intégration du système de parrainage (saisie du code parrain lors de l'inscription)
- Création automatique du profil investisseur
- Conformité RGPD (consentement, politique de confidentialité)

**Temps de développement :** 2 jours

#### Connexion et Sécurité
- Page de connexion personnalisée avec design sur mesure
- Système de récupération de mot de passe par email
- Limitation des tentatives de connexion (protection brute force)
- Session sécurisée avec tokens
- Déconnexion automatique après inactivité
- Conformité aux standards de sécurité WordPress

**Temps de développement :** 1,5 jour

### 2.2 Dashboard Investisseur

#### Vue d'ensemble
- Tableau de bord personnalisé affichant :
  - Nombre total de plants parrainés
  - Montant total investi
  - Rendement estimé
  - Statut des contrats
  - Prochaines récoltes
- Graphiques de performance (évolution des investissements)
- Notifications et alertes importantes
- Accès rapide aux fonctionnalités principales

**Temps de développement :** 3 jours

#### Gestion du Portefeuille
- Liste détaillée des plants parrainés avec :
  - Date d'investissement
  - Numéro de contrat
  - Montant investi
  - Durée du contrat
  - Rendement prévisionnel
  - Statut (actif, en attente, terminé)
- Filtres et recherche avancée
- Export des données (PDF, Excel)
- Historique complet des transactions

**Temps de développement :** 2,5 jours

### 2.3 Système de Parrainage

#### Espace Apporteur d'Affaires
- Dashboard dédié aux apporteurs montrant :
  - Code parrain personnel
  - Nombre de filleuls
  - Commissions générées
  - Statut des paiements de commissions
- Lien de parrainage personnalisé
- Statistiques de performance (taux de conversion)
- Outils de partage sur réseaux sociaux
- Historique des parrainages et commissions

**Temps de développement :** 3 jours

#### Système de Commissions
- Calcul automatique des commissions selon grille définie
- Tableau récapitulatif des commissions par période
- Système de paiement des commissions
- Génération de documents fiscaux
- Notifications de nouvelles commissions

**Temps de développement :** 2 jours

### 2.4 Gestion des Documents

#### Mes Documents
- Bibliothèque de documents personnalisée :
  - Contrats de parrainage signés
  - Factures d'investissement
  - Documents fiscaux
  - Bulletins de récolte
  - Attestations diverses
- Téléchargement sécurisé des documents (PDF)
- Organisation par catégorie et date
- Recherche et filtrage
- Archivage automatique

**Temps de développement :** 2 jours

#### Signature Électronique de Contrats
- Interface de signature électronique intégrée
- Visualisation du contrat avant signature
- Signature par clic avec horodatage
- Génération automatique du PDF signé
- Envoi par email du contrat signé
- Conformité légale (eIDAS, signature simple)
- Historique des signatures

**Temps de développement :** 3 jours

### 2.5 Suivi des Récoltes

#### Mes Récoltes
- Tableau de bord des récoltes avec :
  - Rendement par période
  - Quantité de fraises produites par mes plants
  - Valorisation financière
  - Prochaines distributions prévues
- Historique des récoltes passées
- Calcul du retour sur investissement (ROI)
- Graphiques d'évolution
- Export des données

**Temps de développement :** 2,5 jours

### 2.6 Commande de Produits

#### Boutique Intégrée
- Catalogue de produits (fraises fraîches, confitures, sirops)
- Système de panier d'achat
- Gestion des quantités et stocks
- Prix préférentiels pour les investisseurs
- Système de codes promotionnels
- Calcul automatique des frais de livraison

**Temps de développement :** 3 jours

#### Processus de Paiement
- Intégration Stripe sécurisée :
  - Paiement par carte bancaire
  - Support Google Pay / Apple Pay
  - Mode test et production
- Page de confirmation de commande
- Génération automatique de factures PDF
- Envoi d'emails de confirmation
- Historique des commandes
- Suivi de livraison

**Temps de développement :** 3 jours

### 2.7 Gestion du Profil

#### Mon Profil
- Modification des informations personnelles :
  - Civilité, nom, prénom
  - Email (avec vérification)
  - Téléphone
  - Adresse de facturation
  - Adresse de livraison
- Gestion du mot de passe
- Préférences de communication (newsletters, notifications)
- Données de parrainage (code parrain, filleuls)
- Option de suppression de compte (RGPD)

**Temps de développement :** 2 jours

### 2.8 Système de Rendez-vous

#### Prise de Rendez-vous
- Calendrier interactif de prise de rendez-vous
- Affichage des créneaux disponibles
- Sélection de date et heure
- Confirmation par email
- Rappels automatiques (48h et 24h avant)
- Gestion des annulations/reports
- Synchronisation avec le CRM admin

**Temps de développement :** 3 jours

---

## 3. FONCTIONNALITÉS TECHNIQUES

### 3.1 Architecture du Plugin

- **Architecture orientée objet** (POO) moderne
- **Namespace PHP** pour éviter les conflits
- **Hooks et filtres WordPress** pour extensibilité
- **REST API personnalisée** pour les interactions AJAX
- **Nonces WordPress** pour sécurité CSRF
- **Sanitization et validation** de toutes les données
- **Coding standards WordPress** (PHPCS, WPCS)
- **Compatibilité multisite**
- **Traductions prêtes** (i18n/l10n)

**Temps de développement :** Intégré dans chaque module

### 3.2 Base de Données

- **Tables personnalisées** optimisées :
  - `mpf_investments` - Investissements
  - `mpf_contracts` - Contrats
  - `mpf_commissions` - Commissions de parrainage
  - `mpf_harvests` - Récoltes
  - `mpf_orders` - Commandes
  - `mpf_documents` - Documents
  - `mpf_appointments` - Rendez-vous
- **Relations optimisées** avec foreign keys
- **Indexes** pour performance
- **Scripts de migration** depuis l'ancienne base
- **Système de backup** automatique

**Temps de développement :** 2 jours

### 3.3 Interface Utilisateur

- **Design responsive** (mobile, tablette, desktop)
- **Thème personnalisable** (couleurs, logos)
- **Shortcodes WordPress** pour intégration facile
- **Blocks Gutenberg** pour les fonctionnalités principales
- **AJAX** pour interactions fluides sans rechargement
- **Animations et transitions** modernes
- **Accessibilité** WCAG 2.1 niveau AA
- **Compatible avec les principaux thèmes WordPress**

**Temps de développement :** 3 jours

### 3.4 Sécurité

- **Échappement de toutes les sorties** (XSS prevention)
- **Préparation des requêtes SQL** (injection prevention)
- **Vérification des capacités utilisateur**
- **Nonces sur tous les formulaires**
- **Rate limiting** sur les actions sensibles
- **Chiffrement des données sensibles**
- **Logs d'audit** pour actions critiques
- **Conformité OWASP Top 10**

**Temps de développement :** Intégré dans chaque module

### 3.5 Intégrations Externes

#### Stripe
- Configuration centralisée (clés API)
- Mode test et production
- Webhooks pour synchronisation
- Gestion des erreurs et refus
- Support des remboursements
- Reçus automatiques

**Temps de développement :** 2 jours

#### Emails Transactionnels
- Templates HTML professionnels
- Variables dynamiques
- Support SMTP (IONOS, SendGrid, etc.)
- File d'attente pour envois massifs
- Logs d'envoi
- Gestion des bounces

**Temps de développement :** 1,5 jour

#### Génération de PDF
- DomPDF ou TCPDF intégré
- Templates de contrats personnalisables
- Templates de factures
- Génération de bulletins
- Filigrane et numérotation
- Signature électronique

**Temps de développement :** 2 jours

---

## 4. ADMINISTRATION

### 4.1 Panneau d'Administration WordPress

- **Menu dédié** "Mon Plant Fraise" dans le back-office
- **Dashboard admin** avec statistiques globales :
  - Nombre d'investisseurs
  - Montant total investi
  - Commandes en cours
  - Rendez-vous à venir
- **Gestion des investissements** (liste, édition, suppression)
- **Gestion des contrats** (validation, génération)
- **Gestion des récoltes** (saisie, distribution)
- **Gestion des commandes** (traitement, expédition)
- **Gestion des commissions** (calcul, paiement)
- **Gestion des rendez-vous** (planning, confirmation)
- **Export de données** (Excel, CSV)
- **Configuration du plugin** (paramètres globaux)

**Temps de développement :** 4 jours

### 4.2 Paramètres du Plugin

- **Configuration Stripe** (clés API test/production)
- **Configuration email** (SMTP, templates)
- **Paramètres de parrainage** (taux de commission)
- **Configuration des contrats** (durée, rendement)
- **Paramètres des rendez-vous** (créneaux, durée)
- **Options de notification** (emails, alertes)
- **Configuration des produits** (catalogue, prix)
- **Personnalisation de l'interface** (couleurs, logos)

**Temps de développement :** 1,5 jour

---

## 5. MIGRATION DES DONNÉES

### 5.1 Migration depuis l'Ancienne Base

- **Analyse de la structure** de l'ancienne base MySQL
- **Scripts de migration automatisés** :
  - Utilisateurs et profils
  - Investissements historiques
  - Contrats existants
  - Commissions passées
  - Commandes antérieures
  - Documents archivés
- **Validation des données** migrées
- **Tests de cohérence**
- **Rapport de migration** détaillé

**Temps de développement :** 3 jours

### 5.2 Import de Données

- **Interface d'import** CSV/Excel
- **Mapping de colonnes** flexible
- **Validation en temps réel**
- **Import progressif** (batch processing)
- **Logs d'import** détaillés
- **Rollback en cas d'erreur**

**Temps de développement :** 1,5 jour

---

## 6. TESTS ET QUALITÉ

### 6.1 Tests Unitaires

- Tests PHPUnit pour fonctions critiques
- Couverture de code > 70%
- Tests des calculs financiers
- Tests des webhooks Stripe

**Temps de développement :** 2 jours

### 6.2 Tests d'Intégration

- Tests de bout en bout des parcours utilisateur
- Tests des paiements (mode test Stripe)
- Tests de génération de documents
- Tests d'envoi d'emails

**Temps de développement :** 2 jours

### 6.3 Tests de Sécurité

- Audit OWASP Top 10
- Tests d'injection SQL
- Tests XSS
- Tests CSRF
- Scan de vulnérabilités

**Temps de développement :** 1,5 jour

### 6.4 Tests de Performance

- Tests de charge (100+ utilisateurs simultanés)
- Optimisation des requêtes SQL
- Mise en cache
- Compression des assets

**Temps de développement :** 1,5 jour

---

## 7. DOCUMENTATION

### 7.1 Documentation Utilisateur

- Guide d'utilisation illustré (PDF)
- Tutoriels vidéo pour fonctionnalités principales
- FAQ détaillée
- Guide de dépannage

**Temps de développement :** 2 jours

### 7.2 Documentation Technique

- Documentation du code (PHPDoc)
- Guide d'installation
- Guide de configuration
- Documentation API REST
- Guide de maintenance

**Temps de développement :** 1,5 jour

---

## 8. DÉPLOIEMENT ET FORMATION

### 8.1 Déploiement

- Installation sur serveur de production
- Configuration des clés API
- Migration des données
- Tests post-déploiement
- Mise en production

**Temps de développement :** 1 jour

### 8.2 Formation

- Formation administrateur (2h)
- Formation utilisateur (support vidéo)
- Documentation de prise en main

**Temps de développement :** 1 jour

---

## 9. PLANNING DE DÉVELOPPEMENT

| Phase | Durée | Description |
|-------|-------|-------------|
| **Phase 1 : Fondations** | 5 jours | Architecture, base de données, authentification |
| **Phase 2 : Espace Investisseur** | 8 jours | Dashboard, portefeuille, documents, récoltes |
| **Phase 3 : Parrainage** | 5 jours | Système de parrainage et commissions |
| **Phase 4 : E-commerce** | 6 jours | Boutique, panier, paiement Stripe |
| **Phase 5 : Rendez-vous** | 3 jours | Système de prise de rendez-vous |
| **Phase 6 : Administration** | 5,5 jours | Back-office et configuration |
| **Phase 7 : Migration** | 4,5 jours | Migration données et import |
| **Phase 8 : Tests** | 7 jours | Tests unitaires, intégration, sécurité, performance |
| **Phase 9 : Documentation** | 3,5 jours | Documentation utilisateur et technique |
| **Phase 10 : Déploiement** | 2 jours | Mise en production et formation |

**TOTAL : 50 jours de développement**

---

## 10. CHIFFRAGE DÉTAILLÉ

### 10.1 Développement du Plugin

| Poste | Jours | TJM | Montant |
|-------|-------|-----|---------|
| **Authentification et Compte** | 3,5 | 400€ | 1 400€ |
| **Dashboard Investisseur** | 3 | 400€ | 1 200€ |
| **Gestion du Portefeuille** | 2,5 | 400€ | 1 000€ |
| **Système de Parrainage** | 5 | 400€ | 2 000€ |
| **Gestion des Documents** | 5 | 400€ | 2 000€ |
| **Suivi des Récoltes** | 2,5 | 400€ | 1 000€ |
| **Boutique et Produits** | 3 | 400€ | 1 200€ |
| **Paiement Stripe** | 3 | 400€ | 1 200€ |
| **Gestion du Profil** | 2 | 400€ | 800€ |
| **Système de Rendez-vous** | 3 | 400€ | 1 200€ |
| **Base de Données** | 2 | 400€ | 800€ |
| **Interface Utilisateur** | 3 | 400€ | 1 200€ |
| **Intégrations (Stripe, Email, PDF)** | 5,5 | 400€ | 2 200€ |
| **Administration WordPress** | 5,5 | 400€ | 2 200€ |
| **Migration des Données** | 4,5 | 400€ | 1 800€ |
| **Tests (unitaires, intégration, sécurité)** | 7 | 400€ | 2 800€ |
| **Documentation** | 3,5 | 400€ | 1 400€ |
| **Déploiement et Formation** | 2 | 400€ | 800€ |

**Sous-total Développement : 26 000€**

### 10.2 Gestion de Projet

| Poste | Description | Montant |
|-------|-------------|---------|
| **Chef de projet** | Coordination, suivi, reporting (10% du développement) | 2 600€ |
| **Réunions et communication** | Points hebdomadaires, validation | 800€ |

**Sous-total Gestion : 3 400€**

### 10.3 Outils et Licences

| Poste | Description | Montant |
|-------|-------------|---------|
| **Environnement de développement** | Serveurs de test, staging | 300€ |
| **Outils de tests** | Tests de charge, sécurité | 200€ |

**Sous-total Outils : 500€**

---

## 11. RÉCAPITULATIF DES COÛTS

```
┌────────────────────────────────────────────────────────┐
│                   COÛT TOTAL DU PROJET                 │
├────────────────────────────────────────────────────────┤
│  Développement du plugin           26 000€             │
│  Gestion de projet                  3 400€             │
│  Outils et licences                   500€             │
├────────────────────────────────────────────────────────┤
│  TOTAL HT                          29 900€             │
│  TVA 20%                            5 980€             │
│  TOTAL TTC                         35 880€             │
└────────────────────────────────────────────────────────┘

Délai de réalisation : 50 jours ouvrés (10 semaines)
```

---

## 12. MAINTENANCE ET SUPPORT

### 12.1 Garantie Incluse

- **Garantie de 3 mois** après livraison
- Correction de bugs sans surcoût
- Support technique par email
- Temps de réponse : 48h ouvrées

### 12.2 Maintenance Annuelle (Optionnelle)

| Formule | Description | Prix/an |
|---------|-------------|---------|
| **Basique** | Mises à jour de sécurité, corrections de bugs, support email | 1 500€ |
| **Standard** | Basique + mises à jour WordPress, évolutions mineures (5h/mois) | 3 000€ |
| **Premium** | Standard + monitoring 24/7, support prioritaire, évolutions (10h/mois) | 6 000€ |

---

## 13. MODALITÉS DE PAIEMENT

### 13.1 Échéancier

- **30% à la signature** (10 464€ TTC) - Démarrage du projet
- **40% à mi-parcours** (14 352€ TTC) - Validation des fonctionnalités principales
- **30% à la livraison** (10 764€ TTC) - Mise en production

### 13.2 Moyens de Paiement

- Virement bancaire
- Chèque
- Conditions de paiement : 30 jours net

---

## 14. CONDITIONS GÉNÉRALES

### 14.1 Propriété Intellectuelle

- Le plugin développé est la **propriété exclusive du client**
- Le code source est livré dans son intégralité
- Licence GPL v2+ (compatible WordPress)
- Droit d'utilisation illimité

### 14.2 Évolutions

Toute demande d'évolution hors périmètre défini fera l'objet d'un devis complémentaire sur la base du TJM de 400€.

### 14.3 Délais

Le planning annoncé est indicatif et débute à réception de l'acompte et de tous les éléments nécessaires (accès serveur, contenus, identifiants API).

### 14.4 Validation

Le client s'engage à valider les livrables dans un délai de 5 jours ouvrés. Passé ce délai sans retour, les livrables seront considérés comme validés.

### 14.5 Annulation

En cas d'annulation du projet par le client, les montants déjà versés restent acquis au prestataire au prorata des travaux effectués.

---

## 15. LIVRABLES

À l'issue du projet, le client recevra :

✅ **Plugin WordPress complet** (fichier ZIP installable)
✅ **Code source commenté** (GitHub/GitLab)
✅ **Base de données** (schéma et scripts de création)
✅ **Scripts de migration** des données
✅ **Documentation technique** (PDF + online)
✅ **Documentation utilisateur** (PDF)
✅ **Tutoriels vidéo** (liens YouTube/Vimeo)
✅ **Rapport de tests** (sécurité, performance)
✅ **Guide d'installation et configuration** (PDF)
✅ **Support pendant 3 mois** (email)

---

## 16. COORDONNÉES

**Prestataire :**
[Votre Société]
[Adresse]
[Téléphone]
[Email]
[SIRET]

---

## 17. SIGNATURE

### Le Client (MPF Group)

Nom :  ______________________________

Signature :  ______________________________

Date :  ______________________________


### Le Prestataire

Nom :  ______________________________

Signature :  ______________________________

Date :  ______________________________

---

**Fait en deux exemplaires, le 18 novembre 2025**

*Devis valable 30 jours à compter de la date d'émission*
