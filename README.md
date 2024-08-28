# Markdown-Editor

## Description du Projet

**Markdown-Editor** est une application web interactive développée avec Vue.js qui permet aux utilisateurs de rédiger et de prévisualiser du contenu en Markdown en temps réel. Le texte saisi dans la zone de texte est automatiquement rendu dans un aperçu Markdown. De plus, l'application sauvegarde automatiquement le contenu dans le stockage local du navigateur, permettant aux utilisateurs de retrouver leur travail après un rechargement de la page ou une visite ultérieure.

### Fonctionnalités

- **Éditeur Markdown en temps réel** : Le contenu saisi est instantanément converti et affiché en Markdown.
- **Sauvegarde automatique** : Le texte est sauvegardé dans le stockage local du navigateur, assurant la persistance des données.
- **Récupération du contenu** : À chaque visite ou rechargement de la page, le contenu précédemment saisi est automatiquement chargé.
- **Focus automatique** : La zone de texte est automatiquement focalisée lors du chargement de la page pour une saisie immédiate.

## Configuration du Projet

### Installation des dépendances

```bash
npm install
```
#### Compilation et rechargement à chaud pour le développement

```bash
npm run serve
```

#### Compilation et minification pour la production

```bash
npm run build
```

#### Linting et correction des fichiers

```bash
npm run lint
```