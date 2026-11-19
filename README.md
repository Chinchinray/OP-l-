# OP-là! — app web installable (PWA)

## Contenu
- `index.html` : l'app complète (front office + studio + export)
- `manifest.webmanifest` : nom, icônes, couleurs, raccourci vers le Studio
- `sw.js` : service worker. L'app marche hors ligne après la première visite.
- `icons/` : icônes 180, 192 et 512 px, version maskable pour Android, et SVG

## L'essayer sur ton Mac
Une PWA doit être servie en `https://` ou depuis `localhost`. Double-cliquer sur `index.html` ne suffit pas : le service worker ne démarre pas.

    cd opla-pwa
    ruby -run -e httpd . -p 8000

Ouvre ensuite http://localhost:8000 dans Chrome ou Edge et clique sur l'icône « Installer » dans la barre d'adresse.

## La mettre en ligne
Dépose le dossier `opla-pwa` tel quel sur un hébergeur statique en HTTPS : Netlify Drop, Vercel, GitHub Pages ou Cloudflare Pages.
- **iPhone / iPad** : dans Safari, Partager → « Sur l'écran d'accueil ».
- **Android** : dans Chrome, menu ⋮ → « Installer l'application ».
- **Ordinateur** : dans Chrome ou Edge, icône Installer dans la barre d'adresse.

## Mettre à jour
Après un changement dans `index.html`, change `VERSION` dans `sw.js` (par exemple `opla-v3`) pour que les appareils déjà installés récupèrent la nouvelle version.

## Exports
Dans l'app installée, l'export du Studio télécharge directement un `.zip` : master WAV, stems WAV, MIDI et fichier projet.
