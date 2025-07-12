# 🤖 Workflow n8n : Auto Push vers GitHub + Notification Telegram

Ce projet contient un **workflow automatisé n8n** permettant de :
- 📄 Lire un fichier (ex. `.py`, `.json`, etc.)
- 🔐 L'encoder en **base64**
- 🚀 Le pousser automatiquement sur un **dépôt GitHub** via l’API REST
- ✅ Et en cas de réussite, envoyer une **notification automatique sur Telegram**

---

## 📁 Contenu du repo

workflows/
└── Github_Push.json ← Le fichier exporté du workflow n8n

---

## 🎯 Objectif du Workflow

Ce workflow permet de :
1. Lire un fichier local (ex : `chatbot.py`)
2. Convertir son contenu en base64
3. Utiliser l’API GitHub pour :
   - Créer un commit sur un dépôt
   - Mettre à jour ou créer un fichier
4. Si l’opération réussit ✅ :
   - Envoyer un message Telegram automatiquement

---

## 🔧 Technologies utilisées

| Composant     | Usage                                |
|---------------|--------------------------------------|
| [n8n.io](https://n8n.io)     | Plateforme d'automatisation          |
| GitHub API    | Pousser du code (PUT /repos/...)     |
| Base64        | Encodage du fichier à pusher         |
| Telegram Bot  | Envoi de messages de notification    |

---

## 🛠️ Importer le Workflow dans n8n

1. Ouvre ton interface n8n
2. Clique sur **"Workflows" > "Import from File"**
3. Sélectionne le fichier `auto-push-chatbot.json`
4. Clique sur **"Import"**
5. Tu peux maintenant visualiser et modifier le workflow

---

## 🔑 Pré-requis & Configuration

### GitHub Token (Personnel)
- Va sur [https://github.com/settings/tokens](https://github.com/settings/tokens)
- Génére un token avec le scope `repo`
- Dans le nœud `HTTP Request`, ajoute ce token dans les headers :
Authorization: Bearer ghp_XXXXXXXXXXXXXXXXXXXXXXXXXXX

### Bot Telegram
- Crée un bot via **BotFather**
- Récupère :
- Le **Token du bot**
- Ton **Chat ID** (via [getUpdates](https://api.telegram.org/bot<your-bot-token>/getUpdates))
- Dans le nœud `HTTP Request` (Telegram), configure :
URL : https://api.telegram.org/bot<your-bot-token>/sendMessage
Body Parameters :
chat_id : <ton chat_id>
text : "✅ Le fichier a bien été poussé sur GitHub !"
## 👤 Auteur

> Ce projet a été réalisé par **Chaima Ouerghi** dans le cadre de ses travaux avec **n8n** et GitHub.

