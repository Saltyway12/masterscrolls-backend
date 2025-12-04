MasterScrolls — Backend
_____________________________________________________________________________________________________________________________________________

Assistant MJ professionnel (Laravel 11 + Domain-Driven Architecture)

MasterScrolls est un assistant web conçu pour les Maîtres du Jeu (MJ) de jeux de rôle sur table.
L’objectif : remplacer l’Excel du MJ par un outil moderne, rapide et intelligent, sans remplacer les plateformes existantes (Roll20, Foundry, etc.).

Ce repository contient le backend complet : API, logique métier, authentification, WebSockets et structure du domaine.
_____________________________________________________________________________________________________________________________________________

Stack Technique

Laravel 11
PHP 8.3+
PostgreSQL
Sanctum (authentification API)
Socialite (OAuth : Google, Discord, GitHub)
Architecture Domain-Driven (Ruby mindset)
API REST v1 versionnée
WebSockets (Laravel Echo + Ably/Pusher)
Déploiement Render
_____________________________________________________________________________________________________________________________________________

Architecture du Backend

Le projet suit une structure Domain-Driven, inspirée des pratiques Ruby on Rails.
app/
 ├── Domain/                 # Logique métier (Services, DTO, ValueObjects, Queries)
 │    ├── Campaigns/
 │    ├── Characters/
 │    ├── Creatures/
 │    └── Chapters/
 │
 ├── Application/            # Orchestration des cas d’usage (Auth, Session MJ…)
 │    └── Auth/
 │
 ├── Http/                   # Interface (API v1)
 │    ├── Controllers/Api/V1/
 │    ├── Requests/V1/
 │    └── Resources/V1/
 │
 ├── Models/                 # Eloquent (données persistance uniquement)
 └── ...

Principes :

Contrôleurs minces
Services métier isolés
Models Eloquent minces (relations uniquement)
Value Objects pour les données métiers
DTO pour la transmission propre des données
API versionnée (/api/v1/...)
_____________________________________________________________________________________________________________________________________________

Fonctionnalités Backend (MVP)
Gestion de campagne
Création / édition / archivage
Chapitres narratifs
Bestiaire lié à la campagne

Gestion des personnages (PJ & PNJ):
Statistiques
Compétences
Résistances
Sorts
Inventaire
Code d’accès joueur

Mode Session (Phase 2):
Mise à jour temps réel (HP, états…)
Broadcast WebSockets

Génération de contenu (Phase 3):
PNJ
Rencontres
Donjons textuels
Loot tables
_____________________________________________________________________________________________________________________________________________

Authentification

Sanctum pour les tokens d’API
Socialite pour OAuth :
Google
Discord
GitHub 
_____________________________________________________________________________________________________________________________________________

Déploiement

Le backend est conçu pour être déployé gratuitement sur Render :
Cold-start optimisé
Cache Laravel
Route cache
Build command automatisée
WebSockets via Ably (free tier)
_____________________________________________________________________________________________________________________________________________

Licence

Ce projet est sous licence MIT.
Vous pouvez utiliser, modifier et redistribuer le code librement.
_____________________________________________________________________________________________________________________________________________

Objectif du projet

Servir de base technique exemplaire, réutilisable pour d’autres projets,
et démontrer un niveau professionnel en :

Architecture backend
Domain-Driven Design
API modernes
OAuth
WebSockets
Structuration de projet large
