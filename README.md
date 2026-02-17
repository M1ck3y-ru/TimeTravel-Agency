# ⌚ TimeTravel Agency — Webapp Interactive

> *Explorez l'histoire, réinventée* — Agence de voyage temporel de luxe (fictive)

Projet pédagogique M1/M2 Digital & IA · Webapp interactive créée avec IA générative

---

## 🎯 Description

Webapp single-page pour l'agence fictive **TimeTravel Agency**, permettant aux visiteurs de :
- Découvrir les 3 destinations temporelles avec une interface immersive
- Interagir avec un **agent conversationnel IA** (Chronos)
- Passer un **quiz de personnalisation** pour trouver leur destination idéale
- Explorer les détails de chaque époque et simuler une réservation

---

## 🛠️ Stack Technique

| Technologie | Usage |
|---|---|
| HTML5 / CSS3 / Vanilla JS | Base de l'application (single file) |
| Google Fonts (Playfair Display, Cormorant Garamond, Space Mono) | Typographie premium |
| CSS Animations + IntersectionObserver | Animations au scroll, effets visuels |
| Fetch API | Appels à l'API Anthropic |
| **Claude Sonnet 4.5** (Anthropic API) | Chatbot IA + descriptions personnalisées quiz |

**Architecture** : Single Page Application (SPA) — 1 fichier HTML auto-suffisant, zéro dépendance externe (hors fonts Google + API Anthropic).

---

## ✨ Features Implémentées

### Phase 1 — Structure & Design
- ✅ **Hero section** animée (étoiles scintillantes, anneau temporel rotatif)
- ✅ **Navigation** fixe avec scroll-aware (change au scroll)
- ✅ **Présentation de l'agence** avec portail temporel animé en CSS pur
- ✅ **Design luxury dark mode** : palette obsidian + accents or (#c9a84c)
- ✅ **Responsive** mobile-first (breakpoints 768px et 1024px)

### Phase 2 — Galerie des Destinations
- ✅ **3 destination cards** interactives (Paris 1889, Crétacé, Florence 1504)
- ✅ Hover effects avec reveal des informations et zoom image
- ✅ Badges colorés par destination (bleu Paris, vert Crétacé, rouge Florence)
- ✅ Prix, tags et bouton CTA par destination
- ✅ **Scroll reveal animations** (fade-in au scroll via IntersectionObserver)

### Phase 3 — Intelligence Artificielle

#### 3.1 — Agent Conversationnel "Chronos"
- ✅ Widget chatbot flottant (bottom-right, icône bulle)
- ✅ Fenêtre de chat avec animation d'ouverture
- ✅ **Intégration Claude Sonnet 4.5** via API Anthropic
- ✅ System prompt personnalisé : persona "Chronos", historien passionné
- ✅ Historique de conversation multi-tours maintenu en mémoire
- ✅ Indicateur de frappe animé (3 dots)
- ✅ Suggestions rapides cliquables
- ✅ Fallback local en cas d'erreur API (réponses pré-écrites par destination)
- ✅ Interaction depuis les cards destinations (pré-remplissage du message)

#### 3.2 — Quiz Personnalisation (OPTIONNEL implémenté)
- ✅ **4 questions interactives** (type d'expérience, période, environnement, activité)
- ✅ Barre de progression visuelle (4 dots)
- ✅ Animations de transition entre les étapes
- ✅ **Algorithme de scoring** pour déterminer la destination recommandée
- ✅ **Génération IA de description personnalisée** via Claude (basée sur les réponses)
- ✅ Fallback texte statique si API indisponible
- ✅ Bouton de reset pour recommencer

---

## 🤖 IA Utilisées & Prompts

### Chatbot — System Prompt
```
Tu es Chronos, l'assistant virtuel de TimeTravel Agency, une agence de voyage temporel de luxe fictive.
Ton rôle : conseiller les clients sur nos trois destinations exclusives.
Ton ton : professionnel et chaleureux, passionné d'histoire, enthousiaste mais jamais familier.
[...voir code source pour prompt complet...]
```

### Quiz — Prompt de personnalisation
```
Tu es l'assistant IA de TimeTravel Agency. Un client a répondu à un quiz et ses réponses indiquent: [réponses].
La destination recommandée est [destination].
Génère une description personnalisée de 2 phrases (max 80 mots) qui explique pourquoi cette destination est parfaite pour CE client spécifique.
Sois enthousiaste, évocateur, luxury.
```

### Code — Généré avec
- **Claude Sonnet 4.5** via Claude.ai (interface web directe)

### Visuels
- Placeholders emoji (🗼🦕🎨) — à remplacer par visuels Session 1
- Gradients CSS génératifs par destination

---

## 🎨 Design System

```css
--gold: #c9a84c          /* Accent principal */
--obsidian: #080810      /* Fond principal */
--text: #e8e4d8          /* Texte principal */
--paris: #4a90d9         /* Couleur Paris */
--cretace: #2ecc71       /* Couleur Crétacé */
--florence: #e74c3c      /* Couleur Florence */

Fonts: Playfair Display (titres) + Cormorant Garamond (corps) + Space Mono (labels)
```

---

## 🚀 Installation & Déploiement

### Option 1 — Ouverture directe
```bash
# Ouvrir directement dans le navigateur
open timetravel-agency.html
```

### Option 2 — Serveur local
```bash
python3 -m http.server 8080
# ou
npx serve .
```

### Option 3 — Déploiement Netlify
1. Glisser-déposer le fichier HTML sur [netlify.com/drop](https://app.netlify.com/drop)
2. URL publique générée en 30 secondes

### Option 4 — GitHub Pages
1. Push le fichier dans un repo GitHub
2. Activer GitHub Pages sur la branche main
3. URL : `https://username.github.io/repo-name/timetravel-agency.html`

---

## 📦 Structure du Projet

```
timetravel-agency.html     # Application complète (single file)
README.md                  # Cette documentation
```

---

## ⚙️ Configuration API

Le chatbot utilise l'API Anthropic directement depuis le navigateur (claude.ai environment).

En cas de déploiement standalone, ajouter votre clé API :
```javascript
headers: {
  'x-api-key': 'YOUR_API_KEY',
  'anthropic-version': '2023-06-01',
  'Content-Type': 'application/json'
}
```

---

## 📝 Licence

Projet pédagogique — M1/M2 Digital & IA  
Usage éducatif uniquement — Agence fictive

---

## 🙏 Crédits

| Ressource | Source |
|---|---|
| Code & Architecture | Claude Sonnet 4.5 (Anthropic) |
| Chatbot IA | Claude Sonnet 4.5 via API Anthropic |
| Typographie | Google Fonts (Playfair Display, Cormorant Garamond, Space Mono) |
| Animations | CSS pur (transitions, @keyframes, IntersectionObserver) |
| Hébergement (suggestion) | Netlify / GitHub Pages |

---

## 💡 Réflexion sur le Processus

Cette webapp a été entièrement générée en **vibe coding** avec Claude Sonnet 4.5. Le processus :

1. **Prompt initial** : Brief complet avec toutes les features requises + direction design luxury dark
2. **Itération design** : Précision sur la palette de couleurs, les fonts choisies, les animations
3. **Intégration IA** : Le chatbot utilise le même modèle que celui qui a généré le code, créant une boucle cohérente
4. **Fallbacks** : Implémentation de réponses locales pour garantir le fonctionnement sans API

**Apprentissage clé** : La précision du prompt est déterminante. "Luxury dark mode, accents dorés, fonts serif élégantes" a produit un résultat radicalement supérieur à "beau design".

---

*"Le temps est la ressource la plus précieuse — TimeTravel Agency vous en offre davantage."*
