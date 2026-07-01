<div align="center">

# ⟨ SF / ⟩ — Portfolio de Soufiane Filali

**Développeur Full Stack · Spécialité Cybersécurité · Holberton School Toulouse**

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=threedotjs&logoColor=white)](https://threejs.org/)
[![Formspree](https://img.shields.io/badge/Formspree-FF3E00?style=for-the-badge&logo=formspree&logoColor=white)](https://formspree.io/)

> Portfolio **100% vanilla** — aucun framework, aucun build step, ouverture directe dans le navigateur.

---

</div>

## 📁 Structure du projet

```
portfolio_final/
├── index.html                      ← Page unique (5 sections)
├── cv.html                         ← Visionneuse PDF du CV
├── README.md
├── _headers                        ← Headers sécurité HTTP (Netlify)
│
├── css/
│   └── style.css                   ← ~1 560 lignes de styles
│
├── js/
│   └── script.js                   ← ~1 200 lignes, 15 modules IIFE
│
└── assets/
    ├── videos/
    │   ├── background_cyber.mp4    ← Fond hero
    │   └── test1.mp4               ← Source VideoText
    └── docs/
        ├── soufiane_cv_fullstack.pdf
        └── soufiane_cv_magazine.pdf
```

---

## 🎨 Effets visuels réalisés

### `#home` — Hero

| Effet | Technique |
|-------|-----------|
| **VideoText** — vidéo jouée *à travers* les lettres | Canvas 2D `destination-in` composite |
| **Typewriter** — rôles qui se tapent et s'effacent | `async/await` loop |
| **BlurInUp** — entrée caractère par caractère | `@keyframes blurInUp` + stagger JS |
| **Boutons rainbow** — bordure arc-en-ciel tournante | `@property --rb-angle` + `conic-gradient` |
| Vidéo de fond cybersécurité | `<video autoplay muted loop playsinline>` |

### `#about` — Profil

| Effet | Technique |
|-------|-----------|
| **Starfield** — 340 étoiles animées | Canvas 2D, RAF loop, fade in/out |
| **Globe cyber** — 22 pays, ~15 attaques/sec simulées | Globe.gl v2.27.2 + Three.js r134 |
| Top 10 pays ciblés en temps réel | Tri dynamique d'un objet `hitCount` |
| Feed d'attaques défilant | Injection DOM + animation CSS `feed-in` |
| 5 types d'attaques colorés | DDoS · Malware · Exploit · Scan · Phishing |

### `#stack` — Stack technique

| Effet | Technique |
|-------|-----------|
| **Convoyeur 3D incliné** — 2 rangées infinies | CSS `translateX` + `rotateX(22deg) rotateZ(-7deg)` |
| **Brouillard WebGL interactif** | Vanta.js FOG v0.5.24 |
| Masque de fondu sur les bords | CSS `mask-image: linear-gradient` |

### `#projects` — Projets

| Effet | Technique |
|-------|-----------|
| **Réseau de particules 3D** — 200 nœuds | Canvas 2D, FOV=400, DEPTH=900 |
| Connexions auto entre voisins proches | Distance 2D < 240px → trait alpha |
| **Pulses voyageurs** le long des arêtes | Interpolation linéaire `t ∈ [0,1]`, radial gradient |
| **Belt auto-scroll** draggable | RAF + drag souris + swipe touch |
| **Panel flottant** au survol des cartes | `position: fixed` hors stacking context |
| Bandeau SOON avec shimmer | `@keyframes ribbon-shimmer` |

### `#contact` — Contact

| Effet | Technique |
|-------|-----------|
| **Aurora waves** — 9 vagues sinusoïdales | Canvas 2D + `ctx.filter = 'blur(18px)'` |
| **Orbit 3D** — 3 bulles sociales en ellipse | Trigonométrie, depth scale, opacity dynamique |
| **Fenêtre macOS** — formulaire style éditeur | CSS backdrop-filter, dots colorés, titre centré |
| Envoi email asynchrone | `fetch()` POST → Formspree + feedback live |

### Navigation globale

| Fonctionnalité | Détail |
|----------------|--------|
| **Slides plein écran** | `position: fixed` + transition scale + blur |
| **Dark / Light mode** | View Transitions API — circle reveal depuis le bouton |
| Persistance du thème | `localStorage` |
| Navigation dots | Barre verticale droite, actif = pilule bleue animée |
| Déclencheurs | Molette (accumulator) · Swipe 70px · Flèches clavier · Dots |

---

## 🛠️ Stack technique complète

| Catégorie | Technologie | Version | Usage |
|-----------|-------------|---------|-------|
| Structure | HTML5 | — | Page unique, sémantique |
| Style | CSS3 | — | Custom properties, `@property`, animations |
| Logique | Vanilla JS | ES2022 | 15 modules IIFE indépendants |
| Rendu 2D | Canvas 2D API | — | VideoText, starfield, particules, aurora |
| Globe 3D | Globe.gl | 2.27.2 | Carte cyber attaques simulées |
| WebGL | Three.js | r134 | Moteur pour Vanta FOG |
| Fond 3D | Vanta.js FOG | 0.5.24 | Section Stack |
| Fonts | Space Grotesk · Inter · JetBrains Mono | — | Google Fonts CDN |
| Icônes | Devicon | 2.16.0 | Stack cards |
| Formulaire | Formspree | — | Backend email sans serveur |

---

## 🔒 Sécurité

### Headers HTTP — `_headers` (Netlify)

```http
X-Frame-Options: DENY
X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: camera=(), microphone=(), geolocation=(), payment=()
Strict-Transport-Security: max-age=63072000; includeSubDomains; preload
Content-Security-Policy: default-src 'none'; script-src 'self' [CDNs]; ...
```

### Content Security Policy

```
default-src  'none'
script-src   'self' + 3 CDNs whitelistés exactement
style-src    'self' + Google Fonts + jsDelivr
font-src     fonts.gstatic.com + cdn.jsdelivr.net
img-src      'self' data: blob: unpkg.com
media-src    'self'
connect-src  'self' formspree.io
object-src   'none'
base-uri     'self'
form-action  formspree.io 'self'
```

### Subresource Integrity (SRI) — anti supply chain attack

| Ressource CDN | Hash SHA-384 |
|---------------|--------------|
| `devicon.min.css` | `DjehTlU5SubGD1zUGe78Sk...` |
| `globe.gl.min.js` | `F9OHjeWeuxp9JN/3Cc7Qfq...` |
| `three.min.js` | `9EQoUIJYrv09/oYhSxnw1V...` |
| `vanta.fog.min.js` | `6pWFXNNSqb0oVNIZRz63YH...` |

### Autres protections

- `rel="noopener noreferrer"` sur tous les liens `target="_blank"`
- `maxlength` sur chaque champ : Nom (100) · Email (254) · Message (2000)
- Aucune donnée utilisateur injectée via `innerHTML`
- `autocomplete` sémantique sur les inputs du formulaire
- `aria-live="polite"` sur le statut de formulaire

---

## ⚡ Performance

| Optimisation | Impact estimé |
|--------------|---------------|
| Scripts déplacés en fin de `<body>` | Suppression du render-blocking |
| `dns-prefetch` sur 3 CDN | DNS résolu en avance |
| `preconnect` Google Fonts (DNS + TCP + TLS) | Fonts ~30% plus rapides |
| `font-display: swap` | Pas de texte invisible au chargement |
| `will-change: transform, opacity, filter` | GPU layer sur les sections |
| MutationObserver start/stop | RAF actif uniquement sur la section visible |
| Pas d'inline styles en HTML | CSP `style-src` sans `unsafe-inline` |

---

## 🤖 Projet Agentic

Ce portfolio a été conçu et développé en **collaboration avec Claude Code** (Anthropic) dans une démarche **agentic** : l'IA a généré, itéré, débugué et optimisé l'ensemble du code en temps réel à partir d'instructions en langage naturel.

**Ce que ça illustre :**

- Utilisation d'un agent IA comme co-développeur productif
- Itération rapide sur des effets visuels complexes (Canvas 2D, WebGL, trigonométrie)
- Audit de sécurité et optimisation de performance assistés par IA
- Code produit 100% lisible, maintenu sans framework ni dépendance lourde

> *"L'IA va permettre à n'importe qui d'écrire du code. Comprendre ce code — et savoir le sécuriser — reste humain."*

---

## 🚀 Lancer en local

```bash
# Python (recommandé)
python3 -m http.server 8080

# Node
npx serve .
```

> La vidéo VideoText nécessite un serveur local — les navigateurs bloquent `file://` pour les médias.

---

## 🌐 Déploiement Netlify

Le fichier `_headers` est lu automatiquement par Netlify et active tous les headers de sécurité.

```bash
# Via drag & drop : netlify.com/drop
# Via CLI :
npx netlify deploy --prod --dir .
```

---

<div align="center">

## 👤 Auteur

**Soufiane Filali**

[![GitHub](https://img.shields.io/badge/GitHub-Souf--F-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/Souf-F)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-soufiane--filali--dev-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/soufiane-filali-dev/)
[![Email](https://img.shields.io/badge/Email-sfecom.31000%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:sfecom.31000@gmail.com)

---

*© 2026 — Tous droits réservés*

</div>
