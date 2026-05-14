# 📋 PV Meeting — Compte Rendu Automatique

Application web statique pour générer automatiquement des procès-verbaux de réunion (Zoom, Teams, présentiel) à partir d'une transcription en direct ou importée.

## ✨ Fonctionnalités

- 🎙️ **Transcription en direct** via Web Speech API (Chrome/Edge)
- 📂 **Import de fichiers** `.vtt` (Zoom/Teams), `.srt`, `.txt`
- ⌨️ **Saisie manuelle** par interlocuteur
- 👥 **Distinction des locuteurs** avec code couleur par personne
- 🗒️ **Masque PV personnalisable** avec variables dynamiques
- ✨ **Génération automatique** via Claude (Anthropic API)
- 📄 **Export** en `.md`, `.txt`, impression PDF

## 🚀 Déploiement sur GitHub Pages

### Étape 1 — Créer le dépôt

```bash
# Créer un nouveau dépôt public sur github.com, puis :
git init
git add index.html README.md
git commit -m "Initial commit — PV Meeting app"
git branch -M main
git remote add origin https://github.com/VOTRE_USERNAME/pv-meeting.git
git push -u origin main
```

### Étape 2 — Activer GitHub Pages

1. Aller dans **Settings** → **Pages**
2. Source : `Deploy from a branch`
3. Branch : `main` / `/ (root)`
4. Cliquer **Save**

Votre app sera disponible sous 1-2 minutes à :
`https://VOTRE_USERNAME.github.io/pv-meeting/`

## 🔑 Configuration de la clé API

1. Créez un compte sur [console.groq.com](https://console.groq.com)
2. Générez une clé API (`gsk_...`)
3. Dans l'application, collez votre clé dans le champ **"Clé API Groq (gratuit)"** (en haut à droite)
4. La clé est sauvegardée dans votre navigateur (localStorage) — elle ne quitte jamais votre machine

> **Coût estimé** : environ 0 € — totalement gratuit.

## 📖 Mode d'emploi

### Transcription en direct
1. Ajoutez vos participants dans le panneau gauche
2. Onglet **Transcription** → source **En direct**
3. Sélectionnez le locuteur actif en cliquant sur son nom
4. Cliquez **Démarrer l'écoute** (autorisez le micro)
5. Changez de locuteur à chaque prise de parole

### Import fichier Zoom / Teams
- **Zoom** : exporter la transcription `.vtt` depuis l'enregistrement cloud
- **Teams** : copier/coller la transcription depuis le résumé de réunion en `.txt`
- Format `Prénom Nom : texte` reconnu automatiquement

### Génération du PV
1. Remplissez les métadonnées (titre, date, lieu…)
2. Personnalisez le masque si besoin
3. Cliquez **Générer le PV**
4. Exportez en `.md`, `.txt` ou imprimez

## 🗒️ Variables du masque

| Variable | Contenu |
|---|---|
| `{{DATE}}` | Date de la réunion |
| `{{HEURE}}` | Heure de début |
| `{{LIEU}}` | Lieu ou plateforme |
| `{{OBJET}}` | Titre / objet |
| `{{PRESENTS}}` | Liste des participants |
| `{{ORDRE_DU_JOUR}}` | Ordre du jour |
| `{{ECHANGES_PAR_INTERLOCUTEUR}}` | Résumé par locuteur |
| `{{DECISIONS}}` | Décisions prises |
| `{{ACTIONS}}` | Actions et responsables |
| `{{REDACTEUR}}` | Nom du rédacteur |
| `{{PROCHAINE_REUNION}}` | Date prochaine réunion |

## ⚙️ Compatibilité

| Fonctionnalité | Chrome | Edge | Firefox | Safari |
|---|---|---|---|---|
| Transcription live | ✅ | ✅ | ❌ | ❌ |
| Import fichier | ✅ | ✅ | ✅ | ✅ |
| Saisie manuelle | ✅ | ✅ | ✅ | ✅ |

> La transcription en direct requiert Chrome ou Edge (Web Speech API).

## 🔒 Confidentialité

- Aucun serveur intermédiaire : l'app tourne entièrement dans votre navigateur
- La clé API est stockée uniquement dans votre `localStorage`
- Les transcriptions ne sont jamais envoyées ailleurs qu'à l'API Anthropic pour la génération du PV

---

*Application statique — 1 seul fichier `index.html` — aucune dépendance.*
