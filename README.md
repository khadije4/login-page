# NetNest — Formulaire d'inscription

**NetNest** est un formulaire d'inscription côté client développé en HTML, CSS et JavaScript vanilla, réalisé dans le cadre du cours **Automates et Langages**. Il met en pratique les concepts théoriques des automates finis et des expressions régulières à travers la validation de formulaire en temps réel.

---

## Contexte académique

Ce projet illustre l'application directe des notions vues en cours d'**Automates et Langages** :

- **Expressions régulières (regex)** — chaque règle de validation correspond à un langage régulier reconnu par un automate fini
- **Reconnaissance de motifs** — les champs email, téléphone et mot de passe sont validés par des regex qui modélisent des automates déterministes (AFD)
- **Validation par état** — les messages d'erreur reflètent l'état courant de l'automate (acceptant ou rejetant) à chaque caractère saisi

---

## Fonctionnalités

- **Validation en temps réel** — les erreurs s'affichent au fur et à mesure de la saisie, sans attendre la soumission
- **Validation nom & prénom** — accepte un ou deux mots alphabétiques uniquement
- **Validation email** — vérifie le format `local@domaine.tld` via regex
- **Validation mot de passe** — minimum 10 caractères, une majuscule, un chiffre et un caractère spécial
- **Confirmation du mot de passe** — vérifie que les deux champs sont identiques
- **Validation téléphone** — accepte uniquement les numéros mauritaniens (`+222`, 8 chiffres, séries 2x/3x/4x)
- **Messages d'erreur stylisés** — rouge pour les champs vides/obligatoires, orange pour les erreurs de format

---

## Correspondance Automates ↔ Validation

| Champ             | Expression régulière              | Langage reconnu |
|-------------------|-----------------------------------|-----------------|
| Nom / Prénom      | `/^[A-Za-z]+( [A-Za-z]+)?$/`     | Mots alphabétiques (1 ou 2) |
| Email             | `/^[a-zA-Z0-9]+@[a-zA-Z]+\.[a-zA-Z]{2,}$/` | Adresse email standard |
| Mot de passe      | `/^(?=.*[!@#$%^&*])(?=.*\d)(?=.*[A-Z]).+$/` | MDP fort (lookaheads) |
| Téléphone         | `/^\+222[2-4][0-9]{7}$/`         | Numéros mauritaniens |

---

## Structure du projet

```
netnest/
├── index.html       # Fichier principal — structure, styles et logique de validation

```

---

## Lancement

Aucun serveur ni étape de build n'est nécessaire. Il suffit d'ouvrir `index.html` dans un navigateur moderne :

```bash
# Option 1 — double-cliquer sur le fichier dans l'explorateur
# Option 2 — depuis le terminal
open index.html          # macOS
xdg-open index.html      # Linux
start index.html         # Windows
```

---

## Stack technique

| Couche       | Technologie |
|--------------|-------------|
| Structure    | HTML5 |
| Style        | CSS3 (sans framework) |
| Validation   | JavaScript vanilla (regex + événements DOM) |

---

## Remarques

- Aucun backend ni soumission de formulaire n'est implémenté — il s'agit d'un exercice de validation front-end.
- Le validateur téléphone est restreint aux numéros mauritaniens (`+222`).

---

## Auteurs

Projet réalisé dans le cadre du cours **Automates et Langages**  
Université de Nouakchott
