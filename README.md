# Passation : site DIDUVI XOLA (boutique en ligne)

## Version actuelle (v7, novembre 2026)
`index.html` est désormais la nouvelle version du site (une seule page, chargée par `app.js`). Changements principaux par rapport à la v6 décrite plus bas :
- **Lancement** : précommandes ouvertes, **vente officielle le 27.11.26** (« LA COLLECTION — VENTE OFFICIELLE » dans le hero). Avant cette date, les boutons passent en « PRÉCOMMANDER » et un formulaire email permet de recevoir le lien de paiement en premier.
- **Accueil** : hero « L'Œil de l'Artiste » avec vraie photo (`photos/accueil.jpg`), « La collection — en ligne » et « Le dinner — Bruxelles · sur invitation », date en jaune.
- **Nouvelles sections** : N° 01 La maison, N° 02 L'atelier / L'œil de l'artiste (collection Acte I), N° 03 La trilogie (Acte I : vente + dinner fondateur le 27.11.26 ; mini-métrage *L'Œil de l'Artiste* ; Acte III : défilé en 2027 avec d'autres artistes), N° 04 L'histoire.
- **Produits** :
  - Le Pull, nommé **6°14′ N** (coordonnées) : 175 €, **taille unique**, sur commande, stock limité, pièces numérotées.
  - Le T-shirt, nommé **6°08′ N** : **45 €**, S à XL, coton biologique personnalisé à la main.
- **Délai** : fabriqué à la commande, livré en **1 à 2 semaines**.
- **Livraison Bruxelles** : le créneau se choisit sur deux roues (jour de la semaine + heure de 10:00 à 21:00).
- **Palette** : ajout d'un rouge `#A8231D` et d'un jaune `#F2A51F` ; nouveaux logos « œil jaune » dans `logo/site/`. Typo ajoutée : IBM Plex Mono.
- **Photos réelles** dans `photos/` (pull face/dos, t-shirt face/dos).
- **Pied de page** : liens vers les pages légales, Instagram (lien à renseigner), © DIDUVI XOLA.

Les données (produits, textes légaux, créneaux) sont dans la balise `<script type="text/x-site">` en bas de `index.html`, dans `class Component`.

## Fichiers
- `index.html` : le site (v7), à servir tel quel (Cloudflare Pages).
- `app.js` : moteur d'affichage ; charge React 18.3.1 et Babel depuis unpkg.com.
- `photos/` : photos du shoot.
- `logo/site/` : logos v7 (crème et rouge, œil jaune). `logo/*.svg` : logos v6 (crème, brun, or).
- La maquette v6 (`Site DIDUVI XOLA v6.dc.html`, `support.js`, `image-slot.js`) reste disponible dans l'historique git.

---

## Référence v6 (spécification d'origine)

## En bref
Site e-commerce une seule page pour la marque de vêtements DIDUVI XOLA (Bruxelles). Deux produits : un pull en édition limitée et un t-shirt fait à la commande. Ton luxueux, texte d'abord, palette crème / brun / or.

## À propos des fichiers
`Site DIDUVI XOLA v6.dc.html` est une **maquette de référence en HTML**, pas du code de production. Il faut **recréer** ce design dans la stack de ton choix (Shopify, WooCommerce, Next.js + Stripe/Mollie…). Pour voir la maquette : ouvrir `index.html` dans un navigateur (fichier autonome, marche hors ligne).

## Fidélité
**Haute fidélité** : couleurs, typos, espacements et textes sont définitifs. À reproduire tels quels. Les photos sont des placeholders (le shoot a eu lieu le 14 oct., photos à venir).

## Pages
Navigation : header fixe en 3 colonnes `1fr auto 1fr` — à gauche « Menu », au centre le logo, à droite « Panier (n) ». Padding `18px clamp(18px,4vw,48px)`, texte 10px, majuscules, letter-spacing .24em.
- Sur l'accueil, au-dessus du hero : header transparent, texte et logo crème (`logo/diduvi-signe-creme.svg`).
- Après avoir scrollé au-delà du hero (`scrollY > innerHeight − 90`) et sur les autres pages : fond `#FBF7EF`, logo brun, bordure basse `rgba(44,26,14,.12)`.
- Logo : 40px de haut.

### Menu (plein écran)
Fond `#FBF7EF`. Trois entrées, dans cet ordre : **01 L'Histoire**, **02 Boutique**, **03 Informations**. Typo Rozha One : initiale `clamp(56px,9vw,104px)`, reste du mot en majuscules `clamp(32px,5vw,60px)`. Hover : `#8A5410`. « Be Xola. » en bas, 20px.

### Accueil
1. **Hero** 100vh (min 600px), fond `#2C1A0E`, photo ou vidéo du film en plein cadre.
   - Filtre photo : `sepia(.45) saturate(.6) contrast(1.05) brightness(.82)`.
   - Dégradé par-dessus : `linear-gradient(rgba(26,15,7,.35), rgba(26,15,7,.15) 40%, rgba(26,15,7,.6))`.
   - Au centre : « ACTE I » · **Diduvi Xola** (Caprasimo `clamp(64px,12vw,170px)`) · « TRILOGIE ».
   - En dessous : « L'Œil de l'Artiste » en Rozha One, initiales en grand, reste en petites capitales. Puis « LA COLLECTION ».
   - En bas : lien « BOUTIQUE » souligné.
2. **Boutique** : grille `repeat(auto-fit,minmax(min(100%,340px),1fr))`, gap 56/32px, max-width 1280.
   - Chaque carte : photo 4:5, numéro, nom (Rozha One 36/22px), prix, édition.
3. **L'Histoire** : fond `#2C1A0E`, texte `#F5ECD7`.
   - « Xola » en très grand (`clamp(110px,20vw,280px)`), suivi de la définition.
   - Texte du manifeste sur 2 colonnes justifiées (13.5px / 1.7), « Be Xola. » à droite.

### Page produit
- Haut : 2 colonnes (`minmax(min(100%,420px),1fr)`).
  - Gauche : grande photo (min 560px).
  - Droite :
    - retour « ← LA COLLECTION » et numéro « 01 / 02 » ;
    - édition, nom en très grand, définition façon dictionnaire ;
    - prix (Rozha 30px) avec la mention « TVA COMPRISE » ;
    - choix de taille : la taille choisie est soulignée et en brun, les autres sont en `rgba(44,26,14,.45)` ;
    - bouton « AJOUTER AU PANIER » (fond `#2C1A0E`, hover `#8A5410`, padding 20px). Après le clic, il affiche « AJOUTÉ AU PANIER » et le tiroir du panier s'ouvre.
- Ensuite 3 colonnes 01 / 02 / 03 : La pièce, La façon, La livraison. Bordure gauche `rgba(44,26,14,.18)`, chiffres Rozha 44px `#8A5410`.
- Deux photos carrées côte à côte (détail, dos), séparées de 2px.
- Lien « PIÈCE SUIVANTE → » vers l'autre produit.

### Tiroir panier (à droite)
Largeur `min(420px,100%)`, fond `#FFFDF8`, voile `rgba(44,26,14,.35)`. Contenu :
- les articles du panier ;
- le choix de livraison ;
- le total ;
- un bouton « Voir le panier ».

S'il est vide, le tiroir affiche « Rien encore. ».

### Page Panier
- Titre « PANIER » (P en grand).
- Chaque ligne d'article :
  - vignette 120px ;
  - nom, puis « TAILLE x · 2 SEMAINES » ;
  - quantité : boutons − et + de 36px, et un lien RETIRER ;
  - total de la ligne.
- Bloc livraison :
  - Bruxelles, en main propre : gratuit, avec choix du créneau (Mardi soir, Jeudi soir, Samedi).
  - Belgique / Europe, envoi suivi : 9 €.

### Informations (pages légales)
- À gauche, un menu vertical avec 4 onglets : Mentions légales, Conditions de vente, Livraison et retours, Confidentialité. L'onglet actif a une bordure gauche `#2C1A0E`.
- À droite, le contenu de l'onglet. **Les textes ont des [champs] à compléter** : BCE, TVA, adresse, hébergeur, email.

## Produits et règles
- **Le Pull** : 175 €, tailles **I** et **II**, **20 pièces numérotées** au total. Le stock doit être géré et la vente bloquée à 20.
- **Le T-shirt** : 55 €, tailles S, M, L, XL. Fait à la commande, par séries de 25 à 50, sans limite de stock.
- **Délai** : fabriqué à la commande, livré sous **2 semaines**. À afficher partout : produit, panier, emails.
- **Livraison** :
  - Bruxelles : remise en main propre, gratuite, avec créneau.
  - Belgique / UE : envoi suivi, 9 €.
- **Retours** : 14 jours, si la pièce n'a pas été portée.
- **Paiement** : **Bancontact obligatoire** (Belgique), plus carte. Mollie ou Stripe conviennent.
- **Pas de promo pour le Black Friday.**
- **Deadline** : les ventes doivent être ouvertes bien avant le **21 décembre** (Noël).

## État de l'application
`page` (accueil | boutique | produit | manifeste | legal | panier), `menu`, `cartOpen`, `prodId`, `size`, `cart[] {id, size, qty, prix}`, `ship` (bxl | eu), `slot` (créneau), `tab` (page légale).

## Pages encore à concevoir
Paiement (checkout), confirmation de commande, emails transactionnels (confirmation, expédition / remise). Elles reprennent le même langage visuel.

## Design tokens
**Couleurs**
- Fond du site : `#FBF7EF`
- Crème : `#F5ECD7`
- Surface claire (panier) : `#FFFDF8`
- Brun foncé (texte, fonds sombres) : `#2C1A0E`
- Or / brun accent (liens, hover) : `#8A5410`
- Or clair : `#BA7517`
- Texte secondaire : `#6B5545`
- Fond des photos : `#E9DDC4`
- Lignes : `rgba(44,26,14,.12)`, `.14` et `.18`

**Typographies** (Google Fonts)
- **Caprasimo** : uniquement pour le nom « Diduvi Xola ».
- **Rozha One** : titres, prix, chiffres. Toujours le même principe : l'initiale en grand, le reste en majuscules plus petites avec letter-spacing .04–.06em.
- **Hanken Grotesk** 300 à 600 : texte courant 13.5–15px, interligne 1.7.
- **Étiquettes** : 10px, majuscules, letter-spacing .2 à .3em.

**Forme**
- Aucun arrondi.
- Une seule ombre : celle du tiroir panier, `-20px 0 60px rgba(44,26,14,.15)`.
- Interactions sobres : hover en opacité .6–.85 ou en couleur `#8A5410`.

**Mise en page**
- Marges latérales : `clamp(18px,4vw,48px)`.
- Contenu limité à 1280px de large.
- Espacement vertical entre sections : 88 à 112px.

**Photos** : toutes passent par le même filtre sépia. À reproduire en CSS ou à appliquer directement aux images à l'export.
