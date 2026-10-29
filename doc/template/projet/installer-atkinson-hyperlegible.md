# Installer la police Atkinson Hyperlegible

Note : Ce document a été généré par Claude (Sonnet 5.5 Moyen, le 28/10/2026)

Guide d'installation sur Windows, macOS, Linux, ChromeOS, iOS/iPadOS, Android, le web et LaTeX.

*Dernière vérification des sources : octobre 2026. Les noms de paquets des gestionnaires tiers (Homebrew, apt, pacman, etc.) peuvent évoluer : en cas d'erreur, cherchez avec la commande de recherche du gestionnaire.*

---

## 1. À propos de la police

**Atkinson Hyperlegible** a été conçue par le Braille Institute pour améliorer la lisibilité, notamment pour les personnes malvoyantes. Elle distingue clairement les caractères facilement confondus (I, l, 1, O, 0).

Deux familles existent :

| Famille | Contenu |
|---|---|
| **Atkinson Hyperlegible** (originale, 2021) | 4 styles : normal, italique, gras, gras italique ; 27 langues |
| **Atkinson Hyperlegible Next** (2025) | 7 graisses (ExtraLight à ExtraBold) en droit et italique, version variable, plus de 150 langues |
| **Atkinson Hyperlegible Mono** | Version à chasse fixe, adaptée au code |

**Licence** : SIL Open Font License 1.1 (libre d'usage, y compris commercial).

> **Recommandation** : privilégiez **Atkinson Hyperlegible Next**, plus complète. Le package LaTeX `atkinson` la prend désormais en charge, y compris sous pdfLaTeX (voir section 10).

---

## 2. Sources officielles de téléchargement

- **Braille Institute** : <https://www.brailleinstitute.org/freefont>
- **Google Fonts** : <https://fonts.google.com/specimen/Atkinson+Hyperlegible+Next>
  (originale : <https://fonts.google.com/specimen/Atkinson+Hyperlegible>)
- **Dépôt GitHub (Next)** : <https://github.com/googlefonts/atkinson-hyperlegible-next>
- **Dépôt GitHub (originale)** : <https://github.com/googlefonts/atkinson-hyperlegible>

Le téléchargement fournit une archive `.zip`. À l'intérieur, utilisez de préférence les fichiers `.otf` ou `.ttf` (dossier `fonts/otf` ou `fonts/ttf`).

> Si vous disposez des versions statiques **et** variable, n'installez pas les deux en même temps, afin d'éviter les doublons dans les menus.

---

## 3. Windows

### Méthode graphique

1. Téléchargez l'archive `.zip` et extrayez-la (clic droit → *Extraire tout*).
2. Sélectionnez les fichiers `.otf` ou `.ttf`.
3. Clic droit → **Installer** (pour votre seul compte) ou **Installer pour tous les utilisateurs** (droits administrateur).

Alternative : *Paramètres → Personnalisation → Polices*, puis glissez-déposez les fichiers dans la zone prévue.

### En ligne de commande avec Chocolatey

Un paquet existe pour la version originale :

```powershell
choco install atkinson-hyperlegible
```

### Vérification

Ouvrez Word ou le Bloc-notes : la police doit apparaître dans la liste. Si ce n'est pas le cas, fermez puis relancez l'application.

---

## 4. macOS

### Méthode graphique (Livre des polices)

1. Téléchargez et décompressez l'archive.
2. Double-cliquez sur chaque fichier `.otf` ou `.ttf`.
3. Cliquez sur **Installer la police** dans la fenêtre d'aperçu.

Vous pouvez aussi ouvrir **Livre des polices** et y glisser les fichiers. Choisissez ensuite *Utilisateur* (juste pour vous) ou *Ordinateur* (tous les comptes).

### En ligne de commande avec Homebrew

```zsh
brew install --cask font-atkinson-hyperlegible-next
# ou la version originale :
brew install --cask font-atkinson-hyperlegible
```

Si le nom n'est pas reconnu, cherchez : `brew search atkinson`.

### Installation manuelle (dossier utilisateur)

```zsh
mkdir -p ~/Library/Fonts
cp ~/Downloads/atkinson/fonts/otf/*.otf ~/Library/Fonts/
```

Redémarrez les applications ouvertes.

### Utilisation avec LaTeX (LuaLaTeX/XeLaTeX)

Une police installée dans `~/Library/Fonts` est automatiquement visible par `fontspec`.

---

## 5. Linux

### Installation manuelle (toutes distributions)

```bash
mkdir -p ~/.local/share/fonts/atkinson
cp fonts/otf/*.otf ~/.local/share/fonts/atkinson/
fc-cache -fv
```

Pour une installation **pour tous les utilisateurs**, copiez dans `/usr/local/share/fonts/` (avec `sudo`), puis relancez `fc-cache -fv`.

Vérification :

```bash
fc-list | grep -i atkinson
```

### Paquets de distribution

Les noms ci-dessous sont indicatifs ; vérifiez la disponibilité avec le gestionnaire de votre distribution.

| Distribution | Commande |
|---|---|
| **Debian / Ubuntu** (versions récentes) | `sudo apt install fonts-atkinson-hyperlegible` |
| **Fedora** (dépôt COPR communautaire) | `sudo dnf copr enable julicen/atkinson-hyperlegible-fonts` puis `sudo dnf install atkinson-hyperlegible-next-fonts` |
| **Arch / Manjaro** | Chercher : `pacman -Ss atkinson` ou `yay -Ss atkinson` (AUR) |
| **openSUSE** | `zypper search atkinson` |
| **Nix / NixOS** | `nix search nixpkgs atkinson` |

> Le dépôt COPR Fedora est maintenu par un tiers (non officiel). Utilisez-le en connaissance de cause.

### Environnements de bureau

Après installation, la police est disponible dans GNOME, KDE, Xfce, etc. Pour l'utiliser comme police système :

- **GNOME** : *Ajustements (Tweaks) → Polices*
- **KDE Plasma** : *Paramètres système → Apparence → Polices*

---

## 6. ChromeOS

1. Ouvrez l'application **Fichiers**.
2. Placez les fichiers `.ttf` ou `.otf` dans *Mes fichiers*.
3. ChromeOS ne propose pas d'installation globale de polices. Pour les documents, utilisez **Google Docs/Slides**, où la police est disponible directement (menu des polices → *Plus de polices* → rechercher « Atkinson »).

---

## 7. iOS / iPadOS

Les polices s'installent via un **profil de configuration** ou une application dédiée :

1. Installez une application de gestion de polices (par exemple *iFont*, *AnyFont* ou *Font Diner*).
2. Importez les fichiers `.otf` ou `.ttf` depuis l'application *Fichiers*.
3. Installez le profil proposé : *Réglages → Général → VPN et gestion de l'appareil*.

La police sera ensuite disponible dans les applications qui acceptent des polices personnalisées (Pages, Keynote, Word, etc.).

---

## 8. Android

- **Documents Google** : la police est disponible directement (*Plus de polices*).
- **Autres applications** : la plupart des appareils n'autorisent pas l'installation de polices système sans configuration particulière. Certains constructeurs (Samsung, Xiaomi, etc.) proposent un menu *Réglages → Affichage → Style de police* permettant d'ajouter une police `.ttf`.

---

## 9. Sur le web

### Via Google Fonts

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Atkinson+Hyperlegible+Next:ital,wght@0,200..800;1,200..800&display=swap" rel="stylesheet">
```

```css
body {
  font-family: "Atkinson Hyperlegible Next", system-ui, sans-serif;
}
```

### Auto-hébergement

Pour des raisons de confidentialité (RGPD) ou de performance, vous pouvez héberger les fichiers `.woff2` vous-même. Le projet **Fontsource** permet une installation via npm :

```bash
npm install @fontsource/atkinson-hyperlegible-next
```

```js
import "@fontsource/atkinson-hyperlegible-next";
```

---

## 10. Dans LaTeX

### pdfLaTeX, LuaLaTeX ou XeLaTeX : package `atkinson` (méthode recommandée)

Le package CTAN `atkinson` gère Atkinson Hyperlegible **Next** (toutes les graisses) et la famille **Mono**. Il fournit les polices au format Type 1 : **aucune installation de la police sur le système n'est nécessaire**.

```latex
\usepackage[T1]{fontenc}
\usepackage[sfdefault]{atkinson}   % Atkinson comme police principale
```

- Sans `sfdefault`, Atkinson n'est que la famille sans-serif (`\sffamily`, `\textsf`) et le corps du texte reste en Computer Modern.
- Par défaut, la police **Mono** remplace la police à chasse fixe (`\texttt`, URL, code). L'option `nomono` la désactive.
- Graisses supplémentaires : options `medium`, `light`, `extralight`, `semibold`, `extrabold`.
- Chiffres tabulaires : option `tabular` (ou `t`).
- Ajustement de taille : `scaled=0.95` (ou `scale=0.95`).
- Encodages pris en charge : OT1, T1, TS1 et LY1.
- Mise à jour si votre version est ancienne : `sudo tlmgr update atkinson` ; documentation : `texdoc atkinson`.

Exemple combiné :

```latex
\usepackage[sfdefault,medium,scaled=0.95]{atkinson}
```

### LuaLaTeX ou XeLaTeX avec `fontspec` (alternative)

Utile si vous voulez utiliser les fichiers OpenType installés sur le système (sections 3 à 5). La police doit alors être installée, ou référencée par son chemin :

```latex
\usepackage{fontspec}
\setmainfont{Atkinson Hyperlegible Next}
\setmonofont{Atkinson Hyperlegible Mono}

% Avec fichiers locaux :
\setmainfont{AtkinsonHyperlegibleNext-Regular.otf}[
  Path = ./fonts/,
  BoldFont = AtkinsonHyperlegibleNext-Bold.otf,
  ItalicFont = AtkinsonHyperlegibleNext-Italic.otf,
  BoldItalicFont = AtkinsonHyperlegibleNext-BoldItalic.otf
]
```

Les noms de fichiers exacts dépendent de l'archive téléchargée ; vérifiez-les avant de les reporter.

### Points d'attention

- **Mathématiques** : elles restent en Computer Modern, sauf si vous ajoutez un package adapté.
- **Petites capitales** : Atkinson n'en propose pas ; `\scshape` provoquera un avertissement et sera ignoré.

---

## 11. Dans les IDE et terminaux (police monospace)

Pour utiliser **Atkinson Hyperlegible Mono** :

| Outil | Réglage |
|---|---|
| **IntelliJ IDEA** | *Settings → Editor → Font → Font* |
| **Eclipse** | *Preferences → General → Appearance → Colors and Fonts → Basic → Text Font* |
| **Visual Studio Code** | `"editor.fontFamily": "Atkinson Hyperlegible Mono"` dans `settings.json` |
| **iTerm2** (macOS) | *Settings → Profiles → Text → Font* |
| **Emacs** | `(set-face-attribute 'default nil :family "Atkinson Hyperlegible Mono" :height 130)` |

---

## 12. Dépannage

| Problème | Piste de solution |
|---|---|
| La police n'apparaît pas | Redémarrez l'application (parfois la session) |
| Doublons dans les menus | Désinstallez les versions en trop (statique ou variable) |
| Rendu étrange du gras ou de l'italique | Installez toutes les graisses et styles |
| Erreur « font not found » dans `fontspec` | Vérifiez le nom exact avec `fc-list` (Linux/macOS) ou `luaotfload-tool --find="Atkinson"` |
| Accents ou caractères manquants | Utilisez la famille **Next** (plus de 150 langues) |

---

## 13. Références

- Braille Institute : <https://www.brailleinstitute.org/freefont>
- Google Fonts : <https://fonts.google.com/specimen/Atkinson+Hyperlegible+Next>
- Dépôts GitHub : `googlefonts/atkinson-hyperlegible` et `googlefonts/atkinson-hyperlegible-next`
- Package CTAN `atkinson` : <https://ctan.org/pkg/atkinson>
- Licence : SIL Open Font License 1.1 <https://openfontlicense.org>
