Salut la team ! 👋

Ceci est le repo de base pour le projet client **Aegis** (la néobanque éthique). Ce n'est pas juste un exo, c'est la **base de prod**. On pose ici une **Landing Page** propre et modulaire, en respectant les meilleures pratiques de développement web moderne.

_Note importante : Namcod, Remolut & Aegis sont des entreprises fictives créées dans le cadre d'un exercice pédagogique. Ce document simulé vise à reproduire les conditions réelles du monde professionnel pour l'apprentissage des métiers du développement web._

---

### 💡 Le Vrai Challenge : Le "Zero-Scroll" 

Le client a posé une contrainte qui force l'optimisation maximale : l'expérience doit être **Zero-Scroll** sur mobile.

> "L'interface doit proposer une expérience **zero-scroll sur mobile**, avec une hauteur de vue unique s'adaptant dynamiquement aux dimensions du viewport, nécessitant une optimisation rigoureuse de l'architecture du contenu."

Ça signifie que **tout doit rentrer** dans le *viewport* d'un téléphone. On doit être chirurgical sur le design et le placement des éléments. On a une liberté totale sur l'UX mobile pour y arriver, mais le résultat doit être carré.

---

### 🎨 Éléments Clés & Contraintes Design

Le défi est d'intégrer tous ces éléments dans l'espace contraint, avec un design "Streamer-friendly" :

* **Titre Principal :** "La néobanque éthique & transparente"
* **Action :** CTA principal ("Télécharger l'app").
* **Navigation & Auth :** Menu burger + boutons 's'inscrire' et 'se connecter'.
* **Promo :** Card promotionnelle ("20€ offerts - Mars 2026").
* **Social Link :** Icônes SVG pour Telegram, Mastodon, BlueSky.

#### Contraintes Techniques

* **Mobile-First :** Priorité absolue au layout mobile, avec adaptation desktop distincte.
* **DA Cohérente :** Charte graphique unifiée (grâce aux variables, voir section suivante).

---

### ⚙️ L'Archi Modulaire et le Système de Composants

L'organisation des fichiers reflète les **bonnes pratiques** d'architecture CSS pour un **Design System maison**. On sépare les variables des composants pour que tout soit maintenable.

```

index.html                  → Le fichier HTML principal.
style.css                   → Le fichier CSS principal qui importe tout.
│
├── components/             → Composants UI réutilisables
│   ├── \_all\_components.css → Le point central qui importe tous les composants
│   ├── \_button.css         → Logique du composant Bouton
│   └── \_card.css           → Logique du composant Card
│
└── styles/                 → Organisation des variables & configs
    ├── \_all\_variables.css  → Le point central qui importe toutes les variables
    ├── \_colors.css         → Palette de couleurs sous forme de variables
    ├── \_layout.css         → Variables pour espacements, conteneurs, media queries.
    └── \_decoration.css     → Variables pour les ombres, bordures, etc.

````

#### Le Kiff des Variables CSS

Comme l'an passé, les variables transforment tout :

1.  **Cohérence Visuelle :** Je modifie la `var(--color-primary)` dans `_colors.css` à **un seul endroit**, et tout le site s'adapte automatiquement. Fini les risques !
2.  **Maintenabilité Pro :** Le projet grandit ? On se perd pas dans le CSS. Tout est organisé et nommé de façon logique.
3.  **Langage Commun :** En équipe, tout le monde sait que `var(--spacing-md)` représente l'espacement moyen. C'est plus simple.

#### La Règle BEM (Block, Element, Modifier)

Pour nommer nos classes, on utilise **BEM**. C'est ce qui rend notre CSS hyperlisible et modulaire :

* **Block :** Le composant principal (`.card`).
* **Element :** Une partie du Block (`.card__title`).
* **Modifier :** Une variation du Block (`.card--promo`).

**Le + :** Zéro conflit de styles. On sait direct d'où vient le style et on assure l'indépendance de chaque composant.

---

### 🚀 Comment Contribuer à ce Projet ?

Que vous souhaitiez attaquer une fonctionnalité ou améliorer l'architecture, votre contribution est la bienvenue !

#### 1. Cloner le repository

On passe par SSH, c'est le standard pro (votre clé GitHub doit être OK) :

```bash
# Dans votre terminal
git clone git@github.com:VotreNomUtilisateur/aegis_base.git
cd aegis_base

# Créez une nouvelle branche pour votre feature
git checkout -b feature/ma-nouvelle-feature
````

#### 2\. Pour démarrer rapidement

```bash
# Ouvrez le projet dans VS Code (si vous l'utilisez)
code .

# Ou simplement ouvrez index.html dans votre navigateur préféré
```

**N'oubliez pas** de toujours travailler dans la vue **Mobile** de vos DevTools pour valider le défi *Zero-Scroll* \!

#### 3\. Push & Pull Request

1.  Après avoir codé (en respectant BEM et les variables) :
    ```bash
    git add .
    git commit -m "feat: ajout du composant card selon la spec BEM"
    ```
2.  On push la branche :
    ```bash
    git push origin feature/ma-nouvelle-feature
    ```
3.  On crée une **Pull Request** sur GitHub pour que le code soit revu et mergé.

Bon coding à tou·te·s \! On rend ça propre et scalable \! 💻✨
