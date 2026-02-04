🚀 Projet 4 : CRM Intelligent avec n8n et IA (Analyse & Automatisation)
Ce projet consiste en la création d'un système de gestion de la relation client (CRM) automatisé. Il utilise l'Intelligence Artificielle pour analyser les messages entrants d'un formulaire, définir une priorité et rédiger automatiquement une réponse suggérée dans un fichier Google Sheets.

📋 Fonctionnalités
Capture de données : Récupération des noms et messages via un formulaire n8n.

Analyse par IA : Classification automatique de l'urgence (🔴 URGENT ou 🟢 NORMAL).

Rédaction Assistée : Génération d'un accusé de réception personnalisé et poli par l'IA.

Base de données Cloud : Archivage automatique dans Google Sheets avec horodatage dynamique.

⚙️ Configuration Technique
1. Google Cloud Console (La passerelle)
Pour permettre à n8n d'écrire dans Google Sheets, les configurations suivantes ont été effectuées :

Projet : Création d'un projet dédié nommé "n8n-automation".

API activées : Activation de Google Sheets API et Google Drive API (nécessaire pour lister les fichiers).

Identifiants OAuth 2.0 :

Création d'un ID de client OAuth (Type : Application Web).

Ajout de l'URI de redirection autorisée : http://localhost:5678/rest/oauth2-credential/callback.

Sécurité : Ajout de l'adresse email de test dans la section Audience/Utilisateurs de test pour lever l'erreur access_denied.

2. Configuration du nœud n8n (Google Sheets)
Connexion : Utilisation du Client ID et du Client Secret pour lier n8n au compte Google.

Action : Opération Append Row pour ajouter une nouvelle ligne sans écraser les précédentes.

Mappage des données (Expressions) :

Date : {{ $now }} (Horodatage automatique via le mode Expression fx).

Nom du Client : Récupéré dynamiquement depuis le nœud On form submission.

Analyse/Réponse : Sortie (output) générée par le nœud AI Agent.

3. Le Prompt de l'IA (Intelligence)
L'agent IA a été configuré avec un message système précis :

Rôle : Expert en relation client.

Instructions : Analyser l'urgence, ajouter un badge visuel (🔴/🟢) et rédiger une réponse de deux phrases maximum.

🛠️ Outils utilisés
n8n : Orchestration complète du workflow.

Google Cloud Console : Gestion des accès API et OAuth2.

Google Sheets : Base de données de stockage.

AI Agent (n8n) : Traitement du langage naturel (Analyse & Rédaction).

📈 Résultat final
Le système transforme un message brut en une ligne de données structurée. Dans le tableau final, on retrouve le nom du client, le message d'origine, et le traitement de l'IA incluant la priorité et la réponse suggérée.
