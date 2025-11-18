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

- Formulaire d'inscription personnalisé avec validation avancée
- Validation par email (double opt-in)
- Génération automatique du code parrain unique
- Intégration du système de parrainage
- Page de connexion personnalisée avec design sur mesure
- Système de récupération de mot de passe par email
- Limitation des tentatives de connexion (protection brute force)
- Session sécurisée avec tokens
- Conformité RGPD et standards de sécurité WordPress

### 2.2 Dashboard Investisseur

- Tableau de bord personnalisé (plants parrainés, montant investi, rendement estimé, statut des contrats, prochaines récoltes)
- Graphiques de performance (évolution des investissements)
- Notifications et alertes importantes
- Liste détaillée des plants parrainés avec filtres et recherche
- Export des données (PDF, Excel)
- Historique complet des transactions

### 2.3 Système de Parrainage

- Dashboard dédié aux apporteurs d'affaires
- Code parrain personnel et lien de parrainage personnalisé
- Suivi des filleuls et commissions générées
- Statistiques de performance (taux de conversion)
- Calcul automatique des commissions selon grille définie
- Système de paiement des commissions
- Génération de documents fiscaux

### 2.4 Gestion des Documents

- Bibliothèque de documents personnalisée (contrats, factures, documents fiscaux, bulletins de récolte)
- Téléchargement sécurisé des documents PDF
- Organisation par catégorie et date avec recherche et filtrage
- Interface de signature électronique intégrée
- Visualisation du contrat avant signature
- Génération automatique du PDF signé avec horodatage
- Conformité légale (eIDAS, signature simple)

### 2.5 Suivi des Récoltes

- Tableau de bord des récoltes (rendement par période, quantité de fraises produites, valorisation financière)
- Prochaines distributions prévues
- Historique des récoltes passées
- Calcul du retour sur investissement (ROI)
- Graphiques d'évolution

### 2.6 Commande de Produits

- Catalogue de produits (fraises fraîches, confitures, sirops)
- Système de panier d'achat avec gestion des quantités et stocks
- Prix préférentiels pour les investisseurs
- Système de codes promotionnels
- Intégration Stripe sécurisée (paiement par carte bancaire, Google Pay, Apple Pay)
- Génération automatique de factures PDF
- Historique des commandes et suivi de livraison

### 2.7 Gestion du Profil

- Modification des informations personnelles (civilité, nom, prénom, email, téléphone, adresses)
- Gestion du mot de passe
- Préférences de communication (newsletters, notifications)
- Données de parrainage (code parrain, filleuls)
- Option de suppression de compte (RGPD)

### 2.8 Système de Rendez-vous

- Calendrier interactif de prise de rendez-vous
- Affichage des créneaux disponibles
- Confirmation par email
- Rappels automatiques (48h et 24h avant)
- Gestion des annulations et reports
- Synchronisation avec le CRM admin

---

## 3. FONCTIONNALITÉS TECHNIQUES

### 3.1 Architecture du Plugin

- Architecture orientée objet (POO) moderne
- Namespace PHP pour éviter les conflits
- Hooks et filtres WordPress pour extensibilité
- REST API personnalisée pour les interactions AJAX
- Nonces WordPress pour sécurité CSRF
- Sanitization et validation de toutes les données
- Coding standards WordPress (PHPCS, WPCS)
- Compatibilité multisite
- Traductions prêtes (i18n/l10n)

### 3.2 Base de Données

- Tables personnalisées optimisées (investments, contracts, commissions, harvests, orders, documents, appointments)
- Relations optimisées avec foreign keys
- Indexes pour performance
- Scripts de migration depuis l'ancienne base
- Système de backup automatique

### 3.3 Interface Utilisateur

- Design responsive (mobile, tablette, desktop)
- Thème personnalisable (couleurs, logos)
- Shortcodes WordPress pour intégration facile
- Blocks Gutenberg pour les fonctionnalités principales
- AJAX pour interactions fluides sans rechargement
- Accessibilité WCAG 2.1 niveau AA
- Compatible avec les principaux thèmes WordPress

### 3.4 Sécurité

- Échappement de toutes les sorties (XSS prevention)
- Préparation des requêtes SQL (injection prevention)
- Vérification des capacités utilisateur
- Rate limiting sur les actions sensibles
- Chiffrement des données sensibles
- Logs d'audit pour actions critiques
- Conformité OWASP Top 10

### 3.5 Intégrations Externes

**Stripe**
- Configuration centralisée (clés API test et production)
- Webhooks pour synchronisation
- Gestion des erreurs et refus
- Support des remboursements

**Emails Transactionnels**
- Templates HTML professionnels avec variables dynamiques
- Support SMTP (IONOS, SendGrid, etc.)
- File d'attente pour envois massifs
- Logs d'envoi

**Génération de PDF**
- DomPDF ou TCPDF intégré
- Templates de contrats et factures personnalisables
- Signature électronique

---

## 4. ADMINISTRATION

### 4.1 Panneau d'Administration WordPress

- Menu dédié "Mon Plant Fraise" dans le back-office
- Dashboard admin avec statistiques globales (nombre d'investisseurs, montant total investi, commandes en cours, rendez-vous à venir)
- Gestion des investissements (liste, édition, suppression)
- Gestion des contrats (validation, génération)
- Gestion des récoltes (saisie, distribution)
- Gestion des commandes (traitement, expédition)
- Gestion des commissions (calcul, paiement)
- Gestion des rendez-vous (planning, confirmation)
- Export de données (Excel, CSV)

### 4.2 Paramètres du Plugin

- Configuration Stripe (clés API test/production)
- Configuration email (SMTP, templates)
- Paramètres de parrainage (taux de commission)
- Configuration des contrats (durée, rendement)
- Paramètres des rendez-vous (créneaux, durée)
- Options de notification
- Configuration des produits (catalogue, prix)
- Personnalisation de l'interface (couleurs, logos)

---

## 5. MIGRATION DES DONNÉES

- Analyse de la structure de l'ancienne base MySQL
- Scripts de migration automatisés (utilisateurs, investissements, contrats, commissions, commandes, documents)
- Validation des données migrées
- Tests de cohérence
- Interface d'import CSV/Excel avec mapping de colonnes flexible
- Logs d'import détaillés

---

## 6. TESTS ET QUALITÉ

### Tests Unitaires
- Tests PHPUnit pour fonctions critiques
- Couverture de code > 70%
- Tests des calculs financiers et webhooks Stripe

### Tests d'Intégration
- Tests de bout en bout des parcours utilisateur
- Tests des paiements (mode test Stripe)
- Tests de génération de documents et d'envoi d'emails

### Tests de Sécurité
- Audit OWASP Top 10
- Tests d'injection SQL, XSS, CSRF
- Scan de vulnérabilités

### Tests de Performance
- Tests de charge (100+ utilisateurs simultanés)
- Optimisation des requêtes SQL
- Mise en cache et compression des assets

---

## 7. DOCUMENTATION

### Documentation Utilisateur
- Guide d'utilisation illustré (PDF)
- Tutoriels vidéo pour fonctionnalités principales
- FAQ détaillée

### Documentation Technique
- Documentation du code (PHPDoc)
- Guide d'installation et configuration
- Documentation API REST
- Guide de maintenance

---

## 8. DÉPLOIEMENT ET FORMATION

- Installation sur serveur de production
- Configuration des clés API
- Migration des données
- Tests post-déploiement
- Formation administrateur (2h)
- Documentation de prise en main

---

## 9. RÉCAPITULATIF DES COÛTS

```
┌────────────────────────────────────────────────────────┐
│                   COÛT TOTAL DU PROJET                 │
├────────────────────────────────────────────────────────┤
│  TOTAL HT                          29 900€             │
│  TVA 20%                            5 980€             │
│  TOTAL TTC                         35 880€             │
└────────────────────────────────────────────────────────┘

Délai de réalisation : 10 semaines
```

---

## 10. MAINTENANCE ET SUPPORT

### Garantie Incluse
- Garantie de 3 mois après livraison
- Correction de bugs sans surcoût
- Support technique par email (48h ouvrées)

### Maintenance Annuelle (Optionnelle)

| Formule | Description | Prix/an |
|---------|-------------|---------|
| **Basique** | Mises à jour de sécurité, corrections de bugs, support email | 1 500€ |
| **Standard** | Basique + mises à jour WordPress, évolutions mineures (5h/mois) | 3 000€ |
| **Premium** | Standard + monitoring 24/7, support prioritaire, évolutions (10h/mois) | 6 000€ |

---

## 11. MODALITÉS DE PAIEMENT

### Échéancier
- **30% à la signature** (10 464€ TTC) - Démarrage du projet
- **40% à mi-parcours** (14 352€ TTC) - Validation des fonctionnalités principales
- **30% à la livraison** (10 764€ TTC) - Mise en production

### Moyens de Paiement
- Virement bancaire
- Chèque
- Conditions de paiement : 30 jours net

---

## 12. CONDITIONS GÉNÉRALES

### Propriété Intellectuelle
- Le plugin développé est la **propriété exclusive du client**
- Le code source est livré dans son intégralité
- Licence GPL v2+ (compatible WordPress)
- Droit d'utilisation illimité

### Évolutions
Toute demande d'évolution hors périmètre défini fera l'objet d'un devis complémentaire.

### Délais
Le planning annoncé est indicatif et débute à réception de l'acompte et de tous les éléments nécessaires (accès serveur, contenus, identifiants API).

### Validation
Le client s'engage à valider les livrables dans un délai de 5 jours ouvrés. Passé ce délai sans retour, les livrables seront considérés comme validés.

---

## 13. LIVRABLES

À l'issue du projet, le client recevra :

✅ Plugin WordPress complet (fichier ZIP installable)
✅ Code source commenté (GitHub/GitLab)
✅ Base de données (schéma et scripts de création)
✅ Scripts de migration des données
✅ Documentation technique (PDF + online)
✅ Documentation utilisateur (PDF)
✅ Tutoriels vidéo (liens YouTube/Vimeo)
✅ Rapport de tests (sécurité, performance)
✅ Guide d'installation et configuration (PDF)
✅ Support pendant 3 mois (email)

---

## 14. COORDONNÉES

**Prestataire :**
[Votre Société]
[Adresse]
[Téléphone]
[Email]
[SIRET]

---

## 15. SIGNATURE

### Le Client (MPF Group)

Nom : ______________________________

Signature : ______________________________

Date : ______________________________


### Le Prestataire

Nom : ______________________________

Signature : ______________________________

Date : ______________________________

---

**Fait en deux exemplaires, le 18 novembre 2025**

*Devis valable 30 jours à compter de la date d'émission*
