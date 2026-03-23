# 🤖 Agent Personnel Calendrier — Onyxia

Un agent IA connecté à Telegram qui comprend vos messages texte et vocaux pour gérer vos événements Google Calendar automatiquement.

---

## ✨ Fonctionnalités

- 💬 **Texte & Vocal** — Comprend vos messages écrits et vos notes vocales Telegram
- 📅 **Créer un événement** — Ajoute automatiquement l'événement dans Google Calendar
- 🗑️ **Supprimer un événement** — Supprime un événement sur simple demande
- 🧠 **Mémoire conversationnelle** — L'agent se souvient du contexte de la conversation

---

## 🛠️ Stack technique

| Outil | Rôle |
|---|---|
| **n8n** | Orchestration de l'automatisation |
| **Telegram API** | Déclencheur & réponse (texte + vocal) |
| **Groq LLM** | Compréhension du langage naturel |
| **Groq Whisper** | Transcription des messages vocaux |
| **Google Calendar API** | Création et suppression d'événements |
| **OAuth2** | Authentification sécurisée |

---

## ⚙️ Comment ça fonctionne

```
Telegram (message texte ou vocal)
        ↓
    [If] → détection du type de message
        ↓
  Vocal ? → Téléchargement → Conversion OGA→OGG → Transcription Whisper
        ↓
    Agent IA (Groq) + Mémoire conversationnelle
        ↓
  Créer ou Supprimer un événement Google Calendar
        ↓
  Réponse Telegram à l'utilisateur
```

---

## 🚀 Installation

### Prérequis

- [n8n](https://n8n.io/) (self-hosted ou cloud)
- Un bot Telegram (via [@BotFather](https://t.me/botfather))
- Un compte Google avec Google Calendar activé
- Une clé API [Groq](https://console.groq.com/)

### Étapes

1. **Importer** le fichier `.json` du workflow dans n8n
2. **Configurer** les credentials :
   - Telegram API → token du bot
   - Google Calendar → OAuth2 (autoriser l'accès)
   - Groq → clé API
3. **Activer** l'automatisation
4. **Tester** en envoyant un message à votre bot Telegram :
   > *"Réunion avec le client vendredi à 14h"*

---

## 💬 Exemples d'utilisation

> **Créer un événement**
> *"Ajoute une réunion lundi à 10h"*

> **Depuis un vocal**
> 🎤 *[Message vocal] "N'oublie pas le rendez-vous médecin mercredi à 9h30"*

> **Supprimer un événement**
> *"Supprime la réunion de vendredi"*

---

## 📁 Structure du workflow

```
📦 agent-calendrier/
 ┣ 📄 workflow.json       ← Fichier à importer dans n8n
 ┗ 📄 README.md
```

---

## 👤 Auteur

**Louis Noël — Onyxia**
Automatisations sur mesure avec n8n et l'IA.

- ✉️ [onyxia.noel@gmail.com](mailto:onyxia.noel@gmail.com)
- 💼 [LinkedIn](https://www.linkedin.com/in/louis-noel-5a32543b8)

---

© 2025 Onyxia — Louis Noël
