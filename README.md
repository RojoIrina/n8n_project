# 🤖 Automatisation n8n : Formulaire Intelligent avec IA & Discord

Ce projet démontre une automatisation avancée capable de trier des demandes clients en temps réel grâce à l'Intelligence Artificielle.

## 🚀 Fonctionnement
1. **Capture** : Un formulaire n8n récupère le nom et le message du client.
2. **Analyse IA** : Un Agent IA (Llama 3 via Groq) analyse le message pour déterminer l'urgence.
3. **Notification** : Une alerte personnalisée est envoyée sur Discord avec un badge de priorité (🔴 URGENT ou 🟢 NORMAL).

## 🛠️ Outils utilisés
- **n8n** : Orchestration du workflow.
- **Groq API** : Modèle de langue ultra-rapide pour l'analyse.
- **Discord Webhooks** : Système de notification.

## 📁 Comment utiliser ce projet
Importez le fichier `.json` dans votre instance n8n et configurez vos propres identifiants API pour Groq et Discord.
