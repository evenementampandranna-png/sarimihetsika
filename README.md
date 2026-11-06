# Sarimihetsika – Studio diaporama

Application web pour créer des diaporamas animés à partir de photos et vidéos : effets, transitions, musique, lecture aléatoire et export vidéo.
Tout fonctionne dans le navigateur : aucun serveur, aucune base de données, les fichiers de l'utilisateur ne quittent jamais son appareil.

**Fiteny / Langues :** malagasy, français.

---

## Inona no ataony / Fonctionnalités

| | Malagasy | Français |
|---|---|---|
| Média | Sary (JPG, PNG, WEBP, GIF, HEIC amin'ny Safari) sy vidéo (MP4, MOV, WEBM), fanintonana sy fametrahana | Photos et vidéos, glisser-déposer |
| Effets | Zoom (Ken Burns), panoramique, sivana loko 6 | Zoom, panoramique, 6 filtres |
| Transitions | 13 karazana + kisendrasendra | 13 transitions + aléatoire |
| Mozika | Hira maromaro, fade, fampihenana rehefa misy vidéo, mozika santionany | Playlist, fondu, ducking, musique d'exemple |
| Kisendrasendra | Filaharana vaovao isaky ny mihodina, tsy misy averina | Nouvel ordre à chaque boucle, sans répétition |
| Modely | 8 (Dia, Tsingerin-taona, Fanambadiana, Fahatsiarovana, Fety, Orinasa, Krismasy, 26 Jona) | 8 modèles |
| Soratra | Pejy fanombohana sy famaranana, soratra isaky ny sary, endri-tsoratra 7 | Titres, légendes, 7 polices |
| Avoaka | Vidéo MP4 (Chrome/Edge/Safari) na WebM (Firefox), 720p / 1080p, 16:9 · 9:16 · 1:1 · 4:3 | Export MP4 ou WebM |
| Hafa | Tahiry ho azy, Foanana/Averina, écran feno, mandeha tsy misy internet (PWA) | Sauvegarde auto, annuler/rétablir, plein écran, hors ligne |

Raccourcis clavier : `Espace` lecture/pause · `←` `→` précédent/suivant · `F` plein écran · `S` aléatoire · `Ctrl+Z` / `Ctrl+Y`.

---

## Fametrahana amin'ny GitHub (MG)

1. Midira amin'ny [github.com](https://github.com) → **New repository**. Anarana: `sarimihetsika`. Safidio **Public**, tsindrio **Create repository**.
2. Tsindrio **uploading an existing file**, avelao ao ireo rakitra rehetra ao amin'ity dossier ity (`index.html`, `sw.js`, `manifest.webmanifest`, `icon.svg`, `_headers`, `README.md`), dia **Commit changes**.
3. Mandehana any amin'ny **Settings → Pages**. Ao amin'ny *Build and deployment*, safidio **Deploy from a branch**, branch **main**, dossier **/ (root)**, dia **Save**.
4. Afaka 1–2 minitra, hita ao amin'ny `https://ANARANAO.github.io/sarimihetsika/` ny tranonkala.

## Fametrahana amin'ny Cloudflare Pages (MG)

1. Midira amin'ny [dash.cloudflare.com](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → tabilao **Pages** → **Connect to Git**.
2. Ampifandraiso amin'ny GitHub ary safidio ny repository `sarimihetsika`.
3. Fikirana: *Framework preset* = **None**, *Build command* = (avela ho foana), *Build output directory* = `/`.
4. Tsindrio **Save and Deploy**. Hahazo adiresy toy izao ianao: `https://sarimihetsika.pages.dev`.
5. Isaky ny manova rakitra ao amin'ny GitHub ianao dia miova ho azy koa ny tranonkala ao amin'ny Cloudflare.
6. (Raha tianao) **Custom domains** → ampio ny anaran-tranonkalanao manokana.

> Raha tsy te-hampifandray amin'ny GitHub: **Pages → Upload assets**, avelao ny dossier, dia **Deploy**.

---

## Déploiement sur GitHub Pages (FR)

1. Sur GitHub : **New repository** → nom `sarimihetsika`, **Public** → **Create repository**.
2. **Uploading an existing file** → déposez tous les fichiers de ce dossier → **Commit changes**.
   Ou en ligne de commande :
   ```bash
   git init && git add . && git commit -m "Sarimihetsika v1"
   git branch -M main
   git remote add origin https://github.com/VOTRE-COMPTE/sarimihetsika.git
   git push -u origin main
   ```
3. **Settings → Pages** → *Deploy from a branch* → `main` / `(root)` → **Save**.
4. Le site est en ligne sur `https://VOTRE-COMPTE.github.io/sarimihetsika/`.

## Déploiement sur Cloudflare Pages (FR)

1. **Workers & Pages → Create → Pages → Connect to Git**, choisissez le dépôt.
2. *Framework preset* : **None** · *Build command* : vide · *Build output directory* : `/`.
3. **Save and Deploy** → `https://sarimihetsika.pages.dev`. Chaque `git push` redéploie automatiquement.
4. Le fichier `_headers` ajoute les en-têtes de sécurité et de cache.

---

## Fanamarihana / Notes

- L'export vidéo enregistre en temps réel : la page doit rester ouverte et visible pendant l'export.
- Les projets sont sauvegardés dans le navigateur (IndexedDB) : ils restent sur l'appareil, pas sur un serveur.
- Le partage par lien d'un diaporama (sans exporter de vidéo) nécessiterait un serveur de stockage ; c'est la prochaine étape possible (Cloudflare R2 + Workers).
- Bibliothèque utilisée : [SortableJS](https://github.com/SortableJS/Sortable) (glisser-déposer de la frise), chargée depuis cdnjs.
