## 🌟 AEGIS\_BASE : Landing Page Mobile-First pour une Néobanque Éthique

### Contexte du Projet

Ce projet s'inscrit dans un **cadre pédagogique** simulant la phase de **base d'un projet client** pour la néobanque éthique fictive **Agegis**. L'objectif principal est de développer une **landing page** répondant à des contraintes techniques et d'expérience utilisateur (UX) très précises, notamment sur l'approche **Mobile-First**.

Note importante : Namcod, Remolut & Aegis sont des entreprises fictives créées dans le cadre d'un exercice pédagogique.

---

### Commande Client : Le Défi du "Zero-Scroll"

> "L'interface doit proposer une expérience **zero-scroll sur mobile**, avec une hauteur de vue unique s'adaptant dynamiquement aux dimensions du viewport, nécessitant une optimisation rigoureuse de l'architecture du contenu."

Cette contrainte impose une conception extrêmement rigoureuse et une architecture de contenu optimisée pour garantir que tous les éléments requis tiennent dans le format téléphone, sans dépassement vertical.

---

### 🛠️ Architecture Technique et Design System

L'organisation des fichiers reflète une approche **modulaire et maintenable** du CSS, basée sur un **Design System** et un **Component System** maison.

#### 1. Organisation des Fichiers et Modularité

| Dossier/Fichier | Rôle | Stratégie |
| :--- | :--- | :--- |
| `styles/` | Contient les fichiers de configuration et les variables globales. | **Globalisation** et isolation des configurations (couleurs, variables, layout). |
| `components/` | Contient des blocs UI réutilisables (boutons, cartes, etc.). | **Réutilisabilité** et indépendance des composants (atomisation). |
| `style.css` | Fichier CSS principal. | Importe et agrège toutes les dépendances modulaires (variables, components). |
| `index.html` | La structure de la landing page. | |

#### 2. Logique des Variables CSS (`styles/`)

Les variables CSS personnalisées (`--variable-name`) sont utilisées pour centraliser les valeurs récurrentes (couleurs, polices, espacements).

* **Pourquoi les utiliser ?**
    * **Maintenabilité :** Une seule modification dans `_colors.css` suffit pour changer la charte graphique globale.
    * **Cohérence du Design System :** Elles garantissent l'uniformité des valeurs de design, renforçant la **DA cohérente**.

#### 3. Stratégie de Components et Design System (`components/`)

Le dossier `components/` matérialise le **Component System**. Chaque fichier (ex: `_button.css`, `_card.css`) est un composant UI autonome.

* **Design System :** C'est l'ensemble des règles, principes et outils (y compris le CSS) qui garantissent que le design est cohérent, efficace et réutilisable.
* **Component System :** C'est la mise en œuvre pratique du Design System, où chaque élément d'interface est isolé et stylisé indépendamment, favorisant la **scalabilité**.

#### 4. Adoption de la Méthodologie BEM

La méthodologie **BEM** (Block, Element, Modifier) est privilégiée pour nommer les classes CSS :

* **Block** (Bloc) : L'élément parent indépendant (ex: `.card`).
* **Element** (Élément) : Une partie d'un Bloc qui n'a pas de sens en dehors de celui-ci (ex: `.card__header`).
* **Modifier** (Modificateur) : Un drapeau sur un Bloc ou un Élément pour changer son apparence ou son comportement (ex: `.card--promo`).

**Avantage :** BEM garantit des noms de classes explicites et aide à éviter les collisions de styles, renforçant la **modularité** et la **compréhension** de la structure CSS.

---

### 🎨 Éléments Clés de la Landing Page

Le projet doit intégrer les éléments suivants tout en respectant l'espace contraint du *viewport* mobile pour l'expérience zero-scroll :

* **Navigation & Connexion :** Un menu burger et deux boutons ('s'inscrire' et 'se connecter').
* **Titre Principal :** "La néobanque éthique & transparente".
* **Sous-Titre :** Accrocheur (max 140 caractères).
* **CTA Principal :** "Télécharger l'app" (élément dominant).
* **Card Promotionnelle :** "20€ offerts - Mars 2026".
* **Réseaux Sociaux :** Icônes SVG pour Telegram, Mastodon, BlueSky.
* **Charte Graphique :** Design dynamique et jeune, "Streamer-friendly", sans être immature.

---

### 🚀 Démarrer et Contribuer au Projet

#### 1. Clonage du Projet

Utilisez l'URL SSH pour cloner le dépôt :

```bash
git clone git@github.com:VotreNomUtilisateur/aegis_base.git
cd aegis_base
