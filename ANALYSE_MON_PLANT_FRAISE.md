# Analyse du projet "Mon Plant Fraise"

## Vue d'ensemble

**Mon Plant Fraise** est une plateforme web complète de financement participatif agricole (crowdfarming) pour la culture de fraises en Haute-Savoie, développée par MPF Group.

**Source :** `Mon Plant Fraise.zip` (15.4 MB)

## Concept du projet

Le modèle permet à des particuliers de :
- Parrainer des plants de fraisiers (investissement participatif)
- Suivre la croissance via un espace client personnel
- Recevoir une part de la valeur générée par les ventes et transformations
- Commander des produits (fraises fraîches, confitures, sirops)
- Parrainer d'autres investisseurs via un système d'affiliation

## Architecture technique

### Technologies utilisées

- **Backend :** PHP avec PDO
- **Base de données :** MySQL (OVH/IONOS)
- **Paiements :** Stripe API (supports Google Pay, Apple Pay)
- **Emails :** PHPMailer avec SMTP IONOS
- **Génération PDF :** DomPDF
- **Frontend :** HTML5/CSS3/JavaScript vanilla
- **Design :** Police Montserrat, thème vert olive (#6B8E23)

### Structure du projet

```
/
├── index.php                    # Page d'accueil
├── investir.php                 # Page de parrainage avec prise de RDV
├── commander.php                # Commande de produits
├── espace-client.php            # Dashboard client
├── dashboardapporteur.php       # Dashboard apporteur d'affaires
├── create-checkout-session.php  # Intégration Stripe
├── success.php                  # Page de confirmation post-paiement
├── sign_contract.php            # Signature électronique
├── db_connection.php            # Configuration BDD
├── /admin/                      # Backend administration
│   ├── crm.php                  # CRM complet
│   ├── gestion_contrats.php     # Gestion contrats
│   ├── gestion_documents.php    # Génération documents
│   ├── emailing.php             # Emailings de masse
│   ├── planning.php             # Planning RDV
│   ├── virements.php            # Gestion paiements
│   ├── remboursement.php        # Gestion remboursements
│   └── codepromo.php            # Codes promotionnels
├── /templates/                  # Modèles de contrats HTML
├── /vendor/                     # Dépendances (Stripe, DomPDF)
└── /logs/                       # Journaux d'erreurs
```

## Fonctionnalités principales

### Côté utilisateur

1. **Système d'authentification**
   - Inscription (`register.php`, `process_register.php`)
   - Connexion (`login.php`, `loginapporteur.php`)
   - Reset de mot de passe (`demande_reset.php`, `reset_password.php`)

2. **Parcours d'investissement**
   - Prise de rendez-vous obligatoire avant investissement (`investir.php`)
   - Calendrier interactif avec créneaux disponibles
   - Validation par appel téléphonique

3. **Gestion de portefeuille**
   - Suivi des plants parrainés
   - Historique des investissements
   - Documents contractuels téléchargeables
   - Estimation des rendements

4. **Système de parrainage**
   - Code parrain unique
   - Dashboard apporteur d'affaires
   - Suivi des filleuls et commissions

5. **Commande de produits**
   - Panier d'achat
   - Paiement Stripe sécurisé
   - Génération de factures

6. **Espace client**
   - Profil utilisateur (`profil.php`)
   - Mes documents (`mes_documents.php`)
   - Mes récoltes (`recoltes.php`)
   - Signature de contrats en ligne

### Côté administration

1. **CRM avancé**
   - Gestion complète des utilisateurs
   - Historique des interactions
   - Segmentation des clients

2. **Gestion financière**
   - Suivi des paiements Stripe
   - Gestion des virements
   - Traitement des remboursements
   - Codes promotionnels

3. **Gestion opérationnelle**
   - Planning des rendez-vous
   - Gestion des contrats
   - Génération de documents (PDF)
   - Messagerie interne

4. **Marketing**
   - Système d'emailing de masse
   - Gestion des abonnements newsletter
   - Codes promo et campagnes

## Points critiques de sécurité

### ALERTE : Informations sensibles exposées

**Fichier : `db_connection.php`**

```php
// Ligne 8 : Clé Stripe LIVE en clair
define('STRIPE_SECRET_KEY', 'sk_live_51PDuReFqpvBWmr4W...');

// Lignes 12-16 : Identifiants MySQL en clair
$host_name = 'mpfgloqamo.mysql.db';
$database  = 'mpfgloqamo';
$user_name = 'mpfgloqamo';
$password  = '24021993Ab';
$port = '35917';
```

### Vulnérabilités identifiées

1. **Credentials en clair** - Tous les secrets sont hardcodés
2. **Clé Stripe production** - Risque financier majeur
3. **Absence de .env** - Pas de gestion des variables d'environnement
4. **Potentiel SQL injection** - À vérifier dans les requêtes
5. **CSRF** - Pas de tokens visibles sur les formulaires
6. **Sanitization** - À vérifier sur les inputs utilisateurs

## Recommandations urgentes

### 1. Sécurité (CRITIQUE)

- [ ] **Révoquer immédiatement la clé Stripe** `sk_live_51PDu...`
- [ ] **Changer les identifiants MySQL** exposés
- [ ] Créer un fichier `.env` et déplacer tous les secrets
- [ ] Ajouter `.env` au `.gitignore`
- [ ] Implémenter la validation CSRF sur tous les formulaires
- [ ] Auditer toutes les requêtes SQL pour injection
- [ ] Sanitizer tous les inputs utilisateurs

### 2. Configuration

```php
// Exemple .env recommandé
STRIPE_SECRET_KEY=sk_live_...
STRIPE_PUBLIC_KEY=pk_live_...
DB_HOST=mpfgloqamo.mysql.db
DB_NAME=mpfgloqamo
DB_USER=mpfgloqamo
DB_PASS=nouveau_mot_de_passe_fort
DB_PORT=35917
SMTP_HOST=smtp.ionos.fr
SMTP_USER=info@monplantfraise.com
SMTP_PASS=...
```

### 3. Bonnes pratiques

- [ ] Forcer HTTPS sur toutes les pages
- [ ] Implémenter rate limiting sur login
- [ ] Ajouter 2FA pour les administrateurs
- [ ] Logger toutes les actions sensibles
- [ ] Mettre en place des backups automatiques
- [ ] Configurer `display_errors=0` en production
- [ ] Implémenter Content Security Policy (CSP)
- [ ] Valider et échapper toutes les sorties HTML

### 4. Code quality

- [ ] Séparer la logique métier de la présentation (MVC)
- [ ] Créer des classes pour la réutilisabilité
- [ ] Documenter les fonctions critiques
- [ ] Ajouter des tests unitaires pour les paiements
- [ ] Implémenter un système de cache

## Aspects légaux et réglementaires

Le projet implique des investissements financiers. Points à vérifier :

- [ ] Conformité aux régulations sur le crowdfunding (AMF)
- [ ] Mentions légales sur les risques d'investissement (présentes)
- [ ] RGPD : politique de confidentialité, consentement, droit à l'oubli
- [ ] CGV/CGU pour les contrats de parrainage
- [ ] Agrément ou exemption pour gestion financière collective
- [ ] Assurance responsabilité civile professionnelle

## Qualité du code

### Points positifs

- Architecture fonctionnelle et relativement bien organisée
- Interface utilisateur moderne et responsive
- Intégration propre de Stripe
- Système de templating pour les emails et PDF
- Gestion d'erreurs avec try/catch

### Points d'amélioration

- Pas de framework (considérer Laravel, Symfony)
- Code procédural au lieu d'orienté objet
- Duplication de code (ex: multiples versions `investclient*.php`)
- Absence de tests automatisés
- Pas de gestion de versions pour les assets (cache busting)

## Estimation de maturité

- **Stade actuel :** Prototype fonctionnel / MVP
- **État de production :** NON RECOMMANDÉ sans corrections sécurité
- **Effort de sécurisation :** 2-3 jours de développement
- **Effort de refactoring complet :** 2-3 semaines

## Conclusion

Le projet "Mon Plant Fraise" est une plateforme web ambitieuse et relativement complète pour le financement participatif agricole. Le concept est solide et l'implémentation fonctionnelle démontre une bonne compréhension des besoins métier.

**Cependant**, les problèmes de sécurité critiques (credentials exposés, clé Stripe en clair) rendent le code **DANGEREUX en l'état** pour une mise en production.

**Actions immédiates requises :**
1. Révoquer et régénérer toutes les clés API
2. Sécuriser la configuration
3. Audit de sécurité complet
4. Validation juridique du modèle de crowdfunding

Avec ces corrections, le projet pourrait être viable pour un lancement en production.

---

**Analyse réalisée le :** 2025-11-18
**Fichier source :** Mon Plant Fraise.zip (15,487,061 bytes)
