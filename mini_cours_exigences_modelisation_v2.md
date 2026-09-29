# Mini-cours v2 — Capture & modélisation des exigences
*Aligné sur le cours de M. Hammoudi (E4a, S7) — du cahier des charges à la spécification*

**Règle :** 1 module = 1 notion = 1 exercice de **15 min**. Tu fais l'exo **avant** d'ouvrir les *Corrigés* (fin du doc).
**Objectif :** rendre la modélisation **mécanique** : je lis un mot → je sais quelle construction il déclenche.

---

## 🗺️ La carte du cours (ce que le prof attend vraiment)

Le cours suit **3 étapes**, puis **UML** pour spécifier. Retiens cette colonne vertébrale, tout le reste s'y accroche.

| Étape | But | Ce que tu produis | Modules |
|---|---|---|---|
| **1. Capture** | comprendre le **domaine** et le **problème** | notes d'interview, énoncé nettoyé, questions | A1, A2 |
| **2. Définition** | restituer dans la **langue du client** | exigences, **user stories**, **règles métier**, **dictionnaire** | A3 → A6 |
| **3. Spécification** | décrire **précisément** (prépare la conception) | diagrammes UML | B1 → B7 |
| **✅ Vérifier** | chaque phrase du client est-elle tracée ? | traçabilité + **tests d'acceptation** | A5, C |

**La phrase à écrire en tête de chaque copie :** une exigence dit **le QUOI**, jamais **le COMMENT** (le comment, c'est la conception).

**Le réflexe central :** on ne « réfléchit » pas devant l'énoncé, on le **souligne** : noms, verbes, adjectifs, mots de quantité, mots de temps. Chaque catégorie déclenche une construction.

---
---

# PARTIE A — LES EXIGENCES

# Module A1 — Exigence, parties prenantes, pourquoi c'est dur

## Définition (à savoir réciter)
> **Exigence** = une **capacité** que le système doit fournir, ou une **condition** qu'il doit satisfaire, pour répondre au **besoin d'une partie prenante** (Larman, 2002).

La norme IEEE 830 dit la même chose en deux temps : (1) ce dont un **utilisateur** a besoin pour atteindre un objectif ; (2) ce que le système doit satisfaire pour respecter un **contrat, une norme, un document imposé**.

## Parties prenantes (stakeholders)
Ce n'est **pas** seulement l'utilisateur : client/investisseur, acheteur, utilisateur final, expert du domaine, fournisseur de contenu, développeurs/chefs de projet, examinateur, experts d'un système connexe… **Toute personne qui apporte de la valeur au système.**

| Rôle | Qui c'est | Ce qu'il produit |
|---|---|---|
| **Maître d'ouvrage (MOA)** | le client, celui qui **veut** | cahier des charges **client** (le besoin) |
| **Maître d'œuvre (MOE)** | celui qui **réalise** | cahier des charges **MOE** / spécification (la réponse) |

## Pourquoi c'est dur (question de cours classique)
Le client ne sait pas toujours ce qu'il veut · ses souhaits **évoluent** · il y a des **conflits internes** · client et MOE ne parlent **pas la même langue** · masse d'information énorme · le client **mélange besoin et solution** (« il faut un bouton vert »).

## Sources d'exigences
Cahier des charges, études du projet, modalités de réception, **chaque contact client** ; pour un produit existant : demandes d'évolution, retours clients, stratégie marketing.
**Conseil du cours :** un **référentiel unique** d'exigences — moins il y a de documents, mieux c'est.

## Techniques de capture
Lire la documentation · interviews · réunions de travail · **collecter des exemples** · étudier l'existant et les concurrents · **observer** les utilisateurs au travail · étudier les règles de gestion et les lois.

### ✏️ Exercice A1 (10 min)
Pour le cahier des charges de la **médiathèque** (Module B1) : (1) liste 5 parties prenantes, dont au moins 2 qui **n'utilisent pas** l'application ; (2) donne pour 2 d'entre elles une exigence qui vient **d'elles** ; (3) quelle technique de capture utiliserais-tu pour chacune ?

---

# Module A2 — Nettoyer un énoncé bruité

Un vrai client raconte sa vie, utilise 3 mots pour la même chose et impose des solutions. Ton job : **filtrer**.

## 🔑 Table A2 — Type de bruit → ce que tu fais

| Ce que tu lis | Type de bruit | Ce que tu fais |
|---|---|---|
| Histoire, contexte, anecdote | **bruit pur** | tu rayes |
| « client », « usager », « membre » = même personne | **synonymes** | **un seul terme** → dictionnaire (A6) |
| « rapide », « simple », « moderne », « sécurisé » | **mot flou / subjectif** | tu **quantifies** ou tu poses une question |
| « etc. », « et/ou », « notamment » | **liste ouverte** | tu demandes la liste **complète** |
| « un gros bouton vert », « avec MySQL » | **solution déguisée** | tu extrais le **besoin** (ou contrainte si imposée) |
| « il », « ça », « le système » ambigu | **référence floue** | tu remplaces par le nom exact |
| « normalement », « en général », « souvent » | **règle incomplète** | tu demandes les **exceptions** |
| « pourrait », « devrait », « sera » | **conditionnel / futur** | le cours dit : **à éviter** → présent + « doit » |
| « Mme Durand fera… » | **personne au lieu de rôle** | tu parles en **rôle** (« le gérant ») |

**Règle d'or :** un mot flou n'est **jamais** corrigé en silence. Soit tu le quantifies **en le signalant** (« hypothèse : < 2 s »), soit tu en fais une **question au client**.

### ✏️ Exercice A2 (15 min) — énoncé très bruité
> « Bonjour, je suis Mme Durand, gérante d'une salle de sport à Angers depuis 2015 (on a d'ailleurs refait la peinture l'an dernier). Nos adhérents, enfin nos clients, se plaignent. On voudrait une appli moderne et rapide où les membres pourraient réserver des cours et/ou les annuler, etc. Il faudrait un gros bouton vert pour réserver. Le coach doit voir qui vient. Et il faut que ce soit sécurisé. »

**Fais :** (1) raye le bruit, (2) synonymes à fusionner, (3) mots flous, (4) 5 exigences propres, (5) 3 questions à Mme Durand.

---

# Module A3 — Écrire une bonne exigence

## Le gabarit (mécanique)
```
[ID]  Le système doit  [verbe d'action]  [objet]  [condition / critère mesurable]
EF3   Le système doit  permettre au coach de consulter  la liste des inscrits  à chacun de ses cours.
ENF1  Le système doit  afficher  la confirmation de réservation  en moins de 2 secondes.
```

## Les 8 qualités d'une exigence (liste **du cours** — c'est elle qu'on te demandera)
Groupe-les en 3 familles, c'est plus facile à retenir :

| Famille | Qualité | Test rapide |
|---|---|---|
| **La phrase** | **Atomique** | un **seul** fait ? (pas de « et » qui colle deux besoins) |
| | **Non ambiguë** | une **seule** interprétation ? |
| | **Vérifiable** | je peux écrire un test oui/non ? |
| **Le besoin** | **Correcte** | correspond à un besoin **réel et nécessaire** ? |
| | **Complète** | énoncée **entièrement en un seul endroit** ? |
| | **Cohérente** | ne contredit **aucune** autre exigence ? |
| **La gestion** | **Évaluée** | négociée, **priorisée**, besoin stable ? |
| | **Traçable** | **identifiant unique** + historique des modifications ? |

➕ Le principe transversal : **indépendante de la solution** (le quoi, pas le comment).

**Transformer un but en exigence (exemple du cours) :**
- But (non testable) : « le programme est très simple à utiliser ».
- Exigence : « un testeur non averti découvre **seul** toutes les fonctionnalités **en moins de 15 minutes** ».

Une exigence ne concerne **pas que** utilisateurs et développeurs : « éditer la doc en français et en anglais », « respecter la norme DO-178 » sont aussi des exigences.

## 🔑 Table A3 — Fonctionnelle, non fonctionnelle ou contrainte ?

| Ce que tu lis | Catégorie |
|---|---|
| « pouvoir réserver / calculer / envoyer / consulter » (**action** du système) | **Fonctionnelle (EF)** |
| « en moins de 2 s », « 1 000 utilisateurs simultanés » | **NF — performance** |
| « seuls les admins peuvent », « chiffré », « connexion sécurisée » | **NF — sécurité** |
| « 24h/24 », « 99,9 % du temps » | **NF — disponibilité** |
| « système critique », « pas plus d'1 panne / an » | **NF — fiabilité / sûreté** |
| « utilisable par un débutant en 5 min », « accessible malvoyants » | **NF — ergonomie** |
| « modulaire », « code commenté » | **NF — maintenabilité** |
| « fonctionne sous Windows, macOS et Linux » | **NF — portabilité** |
| « conforme RGPD », « conserver les factures 10 ans » | **NF — légal** |
| « doit tourner sur Android », « doit utiliser l'API de la banque X » | **Contrainte** (imposée, non négociable) |

**Astuce :** « le système **fait** X » → EF. « le système fait X **comment / à quel point** » → ENF.

### ✏️ Exercice A3 (15 min) — réparer des exigences
Pour chaque phrase : quelle qualité est violée, quelle catégorie (EF / ENF / contrainte), réécriture propre.
> a) Le système doit être facile à utiliser.
> b) Le système doit envoyer un SMS et un e-mail et afficher une alerte quand un colis arrive.
> c) Le système doit utiliser une base MySQL pour stocker les commandes.
> d) Les données bancaires doivent être protégées.
> e) Le système doit calculer le total de la commande.
> f) Le système pourrait éventuellement afficher l'historique.
> g) EF4 : « un adhérent peut annuler jusqu'à 2 h avant » ; EF9 : « aucune annulation n'est possible le jour du cours ».

---

# Module A4 — User stories (le cœur du TD)

## Le gabarit (Who / What / Why)
```
En tant que  [rôle]          ← QUI  (un rôle, jamais une personne)
je veux      [objectif]      ← QUOI (une seule action)
afin de      [bénéfice]      ← POURQUOI (la valeur métier)
```
**Exemple du cours :** *En tant qu'apprenti, je veux pouvoir déposer ma fiche de synthèse à la fin de chaque semestre afin de pouvoir réaliser la rencontre tutorale.*

## Les 5 règles du cours
1. **KISS** : rester simple.
2. Parler du **QUOI**, pas du **COMMENT**.
3. Rester dans le **périmètre** du projet et de l'organisation.
4. **Lever l'ambiguïté** des termes (→ dictionnaire).
5. **Réécrire** les US si besoin.

## Le test INVEST (une bonne US est…)

| Lettre | Qualité | Question |
|---|---|---|
| **I** | Indépendante | peut-elle être livrée sans une autre US ? |
| **N** | Négociable | laisse-t-elle place à la discussion (pas un contrat figé) ? |
| **V** | Valeur | apporte-t-elle une valeur **à l'utilisateur** ? |
| **E** | Estimable | l'équipe peut-elle estimer l'effort ? |
| **S** | Small (petite) | tient-elle dans un sprint ? |
| **T** | Testable | peut-on écrire ses tests d'acceptation ? |

## 🔑 Table A4 — Découper une US « composée » (exemple du cours)
Signaux d'une US **trop grosse** : plusieurs verbes liés par **« et » / « ou »**, plusieurs types de données (« infos perso **et** cursus »), des « **à moins que** », « **excepté** ».

```
❌ En tant qu'étudiant, je peux naviguer sur le site, saisir mes informations personnelles
   et celles de mon cursus, et soumettre une demande en ligne, afin d'obtenir des stages.

✅ US1  En tant qu'étudiant, je peux naviguer sur le site afin de consulter les stages proposés.
✅ US2  En tant qu'étudiant, je peux saisir mes informations personnelles et de cursus
        afin de recevoir des propositions adaptées.
✅ US3  En tant qu'étudiant, je peux répondre à une proposition de stage afin d'obtenir
        une réponse à ma candidature.
```
**Méthode :** 1 verbe d'action = 1 US.

## Granularité (vocabulaire Scrum)
**Feature** (grosse fonctionnalité produit) ⊃ **Epic** (grosse story) ⊃ **User Story** (besoin élémentaire) ⊃ **Task** (tâche technique pour réaliser l'US).
Les US vivent dans le **Backlog produit**, sur des **story cards** (titre + gabarit + critères).

## ⚠️ Pièges
- « En tant qu'**utilisateur** » partout → pas assez précis : nomme le **rôle** exact.
- « afin de » qui répète le « je veux » (« je veux me connecter afin de me connecter ») → cherche la **vraie** valeur.
- Une US **technique** (« en tant que développeur je veux une BDD ») → ce n'est pas une US, c'est une **task**.

### ✏️ Exercice A4 (15 min)
Plateforme de réservation de la salle de sport (A2). (1) Écris **3 US** par rôle : Adhérent, Coach, Gérant. (2) Passe-les au test INVEST. (3) Découpe celle-ci : *« En tant que gérant, je veux créer les cours, fixer leur capacité et envoyer le planning aux adhérents et aux coachs afin d'organiser la semaine. »*

---

# Module A5 — Règles métier & tests d'acceptation (BDD)

Une US seule est **trop vague** pour coder. On lui ajoute :
1. les **règles métier (de gestion)** : les conditions à respecter, en **bullet points courts** ;
2. les **tests d'acceptation** : des scénarios qui disent **quand l'US est « finie »**.

## Règles métier — l'exemple du cours
*US : En tant qu'apprenti ingénieur, je veux m'authentifier à la plateforme afin d'accéder à la page d'accueil.*
- La saisie d'un identifiant est obligatoire.
- L'identifiant est une adresse e-mail ESEO.
- La saisie d'un mot de passe est obligatoire.
- Le mot de passe fait au moins 8 caractères.
- Le mot de passe est alphanumérique : au moins un chiffre, une majuscule, une minuscule.
- Le couple identifiant / mot de passe correspond à un compte existant.
- Le compte doit être actif.

**Chemin de pensée pour trouver les règles :** pour chaque **donnée** de l'US, demande-toi → **obligatoire ?** · **format ?** · **bornes (min/max, dates) ?** · **qui a le droit ?** · **dans quel état doit être l'objet ?** · **combien de fois ?**

## Tests d'acceptation BDD (Behaviour Driven Development)
Format **Gherkin** — lisible par le client **et** exécutable par des outils (Cucumber, Reqnroll/SpecFlow) :

```gherkin
Fonctionnalité: Authentification à la plateforme

  Scénario: connexion réussie
    Étant donné un compte actif "jean.dupont@reseau.eseo.fr" avec le mot de passe "Angers2026"
    Quand je saisis cet identifiant et ce mot de passe
    Alors j'accède à la page d'accueil

  Scénario: compte inactif
    Étant donné un compte désactivé "ancien@reseau.eseo.fr"
    Quand je saisis ses identifiants corrects
    Alors l'accès est refusé
    Et le message "Compte inactif" s'affiche

  Plan du scénario: mot de passe invalide
    Quand je saisis le mot de passe "<mdp>"
    Alors le message "<message>" s'affiche
    Exemples:
      | mdp        | message                        |
      | abc        | 8 caractères minimum           |
      | angers2026 | Une majuscule est obligatoire  |
```

| Mot-clé | Rôle | Question |
|---|---|---|
| **Étant donné (Given)** | le **contexte** / état initial | dans quelle situation je suis ? |
| **Quand (When)** | l'**action** | que fait l'acteur ? |
| **Alors (Then)** | le **résultat observable** | que doit-on constater ? |
| **Et / Mais** | enchaîner | — |
| **Plan du scénario + Exemples** | même scénario, plusieurs jeux de données | — |

**La règle mécanique :** **1 règle métier ⇒ au moins 1 scénario**, et pour chaque règle un cas **qui passe** + un cas **qui échoue**.

### ✏️ Exercice A5 (15 min)
*US : En tant qu'adhérent, je veux annuler une réservation afin de libérer ma place.*
(1) Écris 4 règles métier (pense : délai, propriétaire, état de la réservation, liste d'attente). (2) Écris 3 scénarios Gherkin dont au moins un cas d'échec.

---

# Module A6 — Le dictionnaire du domaine

**Objectif :** définir les termes pour que **tout lecteur** comprenne la spécification. C'est un **outil de dialogue** : informel, facile à faire évoluer, réutilisable, et il **détecte les ambiguïtés**.

## Méthode du cours (J.-M. Favre) — mécanique
1. Partir du cahier des charges.
2. **Groupes nominaux** → **notions**.
3. **Groupes verbaux** → **actions** (ou notions).
4. **Éliminer les synonymes** (un seul terme retenu).
5. Éliminer les termes inutiles.
6. Définitions **simples**.
7. Mettre à jour tout au long du projet.

## Le format attendu (celui du TD)

| Notion | Définition | Nom informatique |
|---|---|---|
| Journal de formation | Historique de documents témoignant de la progression sur le volet entreprise… | `JourForm` |

| Action | Définition | Nom informatique |
|---|---|---|
| Déposer fiche de synthèse | Action permettant de déposer la fiche de synthèse à la fin de chaque semestre… | `DepotFS` |

**Règles pour le nom informatique :** court, **sans accent ni espace**, préfixe cohérent (notions en `NomCommun`, actions en `VerbeObjet`). Une définition dit **ce que c'est**, **qui** le manipule, **quand**.

**Le lien avec la suite :** les **notions** deviendront des **classes / attributs** (B2), les **actions** des **cas d'utilisation / opérations** (B1, B2). Le dictionnaire, c'est ton diagramme de classes **en français**.

### ✏️ Exercice A6 (15 min)
Sur l'énoncé de la **médiathèque** (Module B1) : dictionnaire avec **5 notions** et **4 actions** (définition + nom informatique). Signale un synonyme que tu as éliminé.

---
---

# PARTIE B — SPÉCIFIER AVEC UML

Le cours propose une **spécification orientée objets** : identifier les objets (nom, attributs, méthodes), leurs relations, les **interactions** qui réalisent une fonction, et leurs **états**. Chaque diagramme = une **vue**.

| Vue | Diagramme | Question |
|---|---|---|
| Fonctionnelle | **Cas d'utilisation** | qui fait quoi ? |
| Statique | **Classes**, **objets** | quoi existe, comment c'est relié ? |
| Dynamique | **Séquence**, **communication**, **activité**, **états-transitions** | dans quel ordre ? |
| Physique | **Déploiement** (composants) | sur quelles machines ? |

---

# Module B1 — Cas d'utilisation : qui fait quoi

Les cas d'utilisation décrivent, sous forme d'**actions et réactions**, le comportement du système **du point de vue d'un utilisateur**. Ils fixent les **limites du système** (le rectangle) et son **environnement** (les acteurs).

## 🔑 Table B1 — Pattern → cas d'utilisation

| Ce que tu lis | UML |
|---|---|
| un **rôle** humain qui interagit | **acteur** (bonhomme) |
| un **système externe** (banque, mail, capteur) | **acteur secondaire** (souvent à droite, «system») |
| un **but** : verbe + complément (« réserver un cours ») | **cas d'utilisation** (ovale) |
| « X **peut faire tout ce que fait** Y, **et en plus**… » | **généralisation d'acteurs** (triangle vers Y) |
| « pour X, il faut **obligatoirement / toujours** d'abord Y » | **«include»** : flèche **de X vers Y** |
| « lors de X, **éventuellement / si… / en cas de**, on peut Y » | **«extend»** : flèche **de Y vers X** (+ condition, point d'extension) |
| « payer par carte **ou** par virement » | **généralisation de cas** |

**Mnémo :** **include = obligatoire** → la base **a besoin** de l'inclus → la flèche part de la base. **extend = optionnel** → l'extension **s'accroche** à la base → la flèche part de l'extension.

## ⚠️ Pièges classiques
- Le **système** n'est **jamais** un acteur (c'est le rectangle).
- La **base de données interne** n'est pas un acteur.
- « Cliquer sur valider » n'est **pas** un cas : ce n'est pas un **but**. Test : l'acteur repart-il **satisfait** ?
- **Pas d'ordre** entre les cas (ce n'est pas un organigramme).
- N'abuse pas de include/extend : un diagramme lisible vaut mieux qu'un diagramme « complet ».

## La description textuelle (le cours y insiste — souvent notée)
Un ovale ne suffit pas : chaque cas important a sa **fiche**.

```
Cas d'utilisation : Emprunter un document
Résumé            : un usager identifié emprunte un document disponible.
Acteur principal  : Usager
Acteur secondaire : —
Précondition      : l'usager est identifié ; le document est disponible.
Postcondition     : le prêt est enregistré ; le document est indisponible.

Scénario nominal
 1. L'usager présente le document.
 2. Le système vérifie que l'usager n'a pas atteint son quota.
 3. Le système enregistre le prêt et calcule la date de retour.
 4. Le système affiche la date de retour.

Scénarios alternatifs
 2a. L'usager a une pénalité en cours → le système propose de la régler, puis reprend en 3.

Scénarios d'exception
 2b. Quota atteint → le système refuse le prêt. Fin du cas.
```
**Mécanique :** **nominal** = tout se passe bien · **alternatif** = variante qui **rejoint** le nominal · **exception** = on **sort** en échec. Numérote les variantes par l'étape où elles se branchent (2a, 2b).

## Cas d'utilisation ↔ user story
| | User story | Cas d'utilisation |
|---|---|---|
| Taille | petit besoin élémentaire | but complet avec toutes ses variantes |
| Forme | 1 phrase + critères | diagramme + fiche textuelle |
| Culture | agile (Scrum) | UML / processus unifié |
| Lien | **plusieurs US** peuvent détailler **un** cas | un cas regroupe plusieurs US |

### ✏️ Exercice B1 (15 min)
> « Dans notre médiathèque, un usager peut consulter le catalogue sans être connecté. Pour emprunter un document, il doit obligatoirement s'identifier. Lors du retour d'un document, si celui-ci est en retard, le système peut appliquer une pénalité. Un bibliothécaire peut faire tout ce que fait un usager, et en plus enregistrer de nouveaux documents. Les pénalités sont encaissées via le système de paiement bancaire de la ville. »

**Fais :** (1) acteurs, cas, include/extend/généralisation, avec le **mot déclencheur** à côté de chaque flèche ; (2) la **fiche textuelle** de « Retourner un document ».

---

# Module B2 — Diagramme de classes : l'analyse grammaticale mécanique

## 🔑 Table B2 — Nature du mot → élément UML

| Ce que tu soulignes | Devient | Exemple |
|---|---|---|
| **Nom** qui a une vie propre (on le crée, supprime, compte) | **classe** | Station, Vélo, Abonné |
| **Nom** qui est une simple **valeur** | **attribut** | `- dateDebut : Date` |
| **Verbe d'action** sur un objet | **opération** | `+ calculerTotal() : float` |
| **Verbe de lien** (possède, contient, gère, concerne) | **association** (avec un nom + sens de lecture ▸) | Client — Compte |
| « **est un** », « **sont des** », « **types de** » | **héritage** | Chien ▷ Animal |
| **Liste fermée** de valeurs | **énumération** | `{ MENSUEL, ANNUEL }` |
| **Adjectif** qui change (disponible, payé) | attribut booléen — ou **état** si plusieurs valeurs (→ B6) | `- disponible : boolean` |
| Donnée qui dépend du **couple** (A, B) | **classe d'association** | Inscription.note |
| Mot de **quantité** (« un », « plusieurs », « au plus 3 ») | **multiplicité** | `0..1`, `1`, `*`, `1..*`, `0..3` |

**Test « classe ou attribut ? »** : ce nom a-t-il lui-même des caractéristiques ? « Adresse » (rue, ville, CP) → classe. « Couleur » → attribut.

**Visibilités :** `+` public · `-` privé · `#` protégé · `~` package. Par défaut : attributs `-`, opérations `+`.

## Multiplicités : la lecture qui ne rate jamais
On lit **depuis une instance de la classe opposée** : `Client 1 ——— * Compte` se lit « **un** compte appartient à **1** client » et « **un** client a **plusieurs (*)** comptes ». La multiplicité est écrite **du côté de la classe qu'on compte**.

---

## 🧬 B2.1 — L'héritage, reconnu d'instinct
**Signaux :** « est un », « sont des », « il existe plusieurs **types / sortes / catégories** de », « se décline en », « **soit** un X, **soit** un Y ».

**Test des 3 questions** (3 × oui → héritage) : 1. **Est-un ?** 2. **Toujours** (toute sa vie) ? 3. **Différence réelle** (attribut ou comportement en plus) ?

| Situation | Bonne réponse |
|---|---|
| 3 × oui | **héritage** |
| Sous-types qui ne diffèrent **que par un libellé** | **énumération** / attribut `type` |
| Le « type » **change dans le temps** (étudiant **puis** salarié) | **rôle** : association, **pas** héritage |
| « on ne crée jamais un X générique » | parent **abstrait** (nom en *italique* ou `{abstract}`) |
| « chacun calcule X **à sa façon** » | opération **abstraite** dans le parent, **redéfinie** dans chaque enfant |

## 🧩 B2.2 — Composition vs agrégation vs association (arbre de décision)
```
Q1. Relation « tout / partie » ?  (« composé de », « contient », « fait partie de »)
      ├── NON ───────────────────────────────►  ASSOCIATION simple    ─────
      └── OUI
           Q2. Si le tout disparaît, la partie disparaît-elle ?
               La partie peut-elle être partagée ou changer de tout ?
                ├── disparaît / jamais partagée ─►  COMPOSITION   ◆───  (losange PLEIN)
                └── survit / partagée / réaffectée ►  AGRÉGATION   ◇───  (losange CREUX)
```

| Mots de l'énoncé | Verdict |
|---|---|
| « est composé de », « comporte », « n'a pas de sens sans », « **supprimé avec** » | **composition ◆** |
| « regroupe », « rassemble », « **continue d'exister** », « **réaffecté** », « **partagé** » | **agrégation ◇** |
| « a un », « concerne », « est associé à », « est responsable de » | **association** |

**Rappels :** losange **côté tout** · en composition, multiplicité côté tout **au plus 1** (`1` ou `0..1`) · doute agrégation/association → l'association est acceptée · doute composition/agrégation → **cherche le mot de durée de vie**.

## 🧷 B2.3 — Ce que la v1 ne couvrait pas (et qui est dans ton cours)

**Classe d'association** — quand une donnée n'appartient ni à A ni à B mais au **couple** :
```
Etudiant  * ────────┬──────── *  Cours
                    ┊
             ┌──────┴──────┐
             │ Inscription │
             │ - note      │
             └─────────────┘
```
⚠️ Une classe d'association impose **un seul lien par couple** (A, B). Si le même couple peut se répéter (un abonné loue **plusieurs fois** le même vélo) → fais une **vraie classe** intermédiaire.

**Navigabilité** — la flèche dit **qui connaît qui** :
`Commande ──────▸ Client` : une commande connaît son client (en Java : `private Client client;` dans `Commande`), le client ne connaît pas ses commandes. Sans flèche = navigable dans les deux sens (ou non précisé).

**Rôles** — au bout d'une association on peut écrire le rôle joué : `Personne ——employé * / 1 employeur—— Entreprise`.

**Associations réflexives** — une classe reliée à elle-même : `Salarié —encadre→ Salarié` (0..1 chef / * subordonnés).

**Contraintes** — les multiplicités ne disent pas tout. Exemple du cours : un client A a un compte C, C appartient à la banque B → **A doit être client de B**. On l'écrit en **note** `{contrainte}` (ou en OCL). Autres contraintes utiles : `{ordered}`, `{unique}`, `{frozen}`.

**Arité** — une association relie en général 2 classes ; une association **ternaire** (losange au centre) relie 3 classes (Enseignant–Cours–Salle).

### ✏️ Exercice B2a (10 min) — détection éclair
Héritage / composition / agrégation / association / énumération / classe d'association / **piège** (rôle ou attribut).
> 1. Un immeuble est composé d'appartements.
> 2. Une playlist contient des morceaux.
> 3. Les salariés et les stagiaires sont des personnes qui travaillent dans l'entreprise.
> 4. Une facture comporte des lignes de facture.
> 5. Un cours a un enseignant responsable.
> 6. Un véhicule est soit une voiture, soit une moto ; chacun calcule sa taxe différemment.
> 7. Une commande a un statut : en attente, payée ou expédiée.
> 8. Une personne peut être étudiante, puis devenir salariée.
> 9. Un département regroupe des enseignants ; s'il ferme, les enseignants sont réaffectés.
> 10. Il existe des livres papier et des livres numériques ; ils se gèrent exactement pareil.
> 11. Pour chaque étudiant et chaque matière, on enregistre une note.
> 12. Un salarié peut encadrer d'autres salariés.

### ✏️ Exercice B2b (15 min) — énoncé bruité → diagramme de classes
> « Notre agence de location de vélos (fondée par deux amis passionnés de montagne !) possède plusieurs stations dans la ville. Chaque station comporte des bornes ; une borne n'existe pas en dehors de sa station. Un vélo peut être garé sur une borne, ou être en circulation. Il existe des vélos classiques et des vélos électriques ; ces derniers ont un niveau de batterie. Un abonné — on dit aussi client ou utilisateur — effectue des locations. Pour chaque location, on enregistre l'heure de départ et l'heure d'arrivée. L'abonnement est mensuel ou annuel. »

**Fais :** nettoie (A2), puis le diagramme de classes avec multiplicités. Justifie chaque losange.

---

# Module B3 — Diagramme d'objets : la photo d'un instant

Le diagramme de **classes** = le **moule** (toujours vrai). Le diagramme d'**objets** = une **photo** du système à un instant précis.

| | Classe | Objet |
|---|---|---|
| Nom | `Velo` | `v12 : VeloElectrique` (**souligné**) ou `: Velo` (anonyme) |
| Attributs | `- batterie : int` | `batterie = 80` (valeur) |
| Relations | associations + multiplicités | **liens** (pas de multiplicité : 1 lien = 1 trait) |

**À quoi ça sert :** **illustrer** un cas concret et surtout **vérifier** un diagramme de classes : si tu n'arrives pas à dessiner une situation réelle sans violer une multiplicité, ton diagramme de classes est faux.

### ✏️ Exercice B3 (10 min)
Avec ton diagramme B2b, dessine la situation : *la station « Gare » a 2 bornes ; le vélo électrique v7 (batterie 45 %) est sur la borne 1 ; l'abonnée Léa loue le vélo classique v3 depuis 8h10.* Vérifie qu'aucune multiplicité n'est violée.

---

# Module B4 — Interactions : séquence & communication

Le diagramme de **séquence** montre **une conversation entre objets pour UN scénario** (souvent le scénario nominal d'un cas d'utilisation), **le temps s'écoulant vers le bas**.

## Syntaxe (à connaître par cœur)
```
   :Usager          :Borne            :Pret
     │                 │
     │ emprunter(doc)  │                          ← message synchrone (flèche pleine ▶)
     │────────────────▶█
     │                 █  new(doc, usager)        ← création : la flèche pointe la TÊTE de l'objet
     │                 █──────────────────────▶ ┌──────┐
     │                 █                        │:Pret │
     │                 █◀ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ └──┬───┘   ← retour (pointillé)
     │ dateRetour      █                           │
     │◀─ ─ ─ ─ ─ ─ ─ ─ █                           │
     │                 │                           ✕     ← destruction (croix en bas de ligne de vie)
```
| Élément | Signe |
|---|---|
| **Objet** | rectangle `nom : Classe` en haut |
| **Ligne de vie** | trait pointillé vertical |
| **Activation** | rectangle fin sur la ligne de vie (l'objet travaille) |
| **Message synchrone** | flèche pleine, tête pleine (l'appelant attend) |
| **Message asynchrone** | flèche à tête ouverte (l'appelant n'attend pas) |
| **Retour** | flèche pointillée |
| **Création / destruction** | `new(...)` vers la tête de l'objet / croix ✕ |

## Fragments combinés (les mots qui les déclenchent)
| Mot de l'énoncé | Fragment |
|---|---|
| « pour chaque », « tant que », « jusqu'à » | **`loop`** `[condition]` |
| « si… sinon », « selon le cas » | **`alt`** (compartiments séparés par pointillés, chacun avec `[garde]`) |
| « éventuellement », « optionnellement » | **`opt`** `[condition]` |
| « en parallèle » | **`par`** |

## Séquence vs communication (collaboration)
Même information, **deux mises en page** :
- **Séquence** → met l'accent sur l'**ordre temporel** (axe vertical).
- **Communication** → met l'accent sur la **structure** : objets reliés par des **liens**, messages **numérotés** (`1`, `1.1`, `1.2`, `2`) pour retrouver l'ordre.

**Réflexe :** chaque message reçu par un objet = une **opération** de sa classe. Le diagramme de séquence **complète** le diagramme de classes (et le vérifie).

### ✏️ Exercice B4 (15 min)
Scénario : *un abonné demande à louer un vélo à une borne. La borne vérifie l'abonnement auprès du système. Si l'abonnement est valide, la borne crée une location et libère le vélo ; sinon elle affiche un refus.* Dessine le diagramme de séquence (avec `alt`), puis la version **communication** (messages numérotés).

---

# Module B5 — Diagramme d'activités : un processus

## 🔑 Table B5 — Mot → construction
| Ce que tu lis | Construction |
|---|---|
| « d'abord », « puis », « ensuite », « enfin » | actions enchaînées (flèches) |
| « si… sinon », « dans le cas où » | **décision** ◇ + gardes `[condition]` |
| retour de branches alternatives | **fusion** ◇ (merge) |
| « en parallèle », « simultanément » | **fork** (barre noire, 1 entrée → n sorties) |
| « quand les deux sont terminés » | **join** (barre noire, n entrées → 1 sortie) |
| « pour chaque », « tant que », « recommencer » | **itération** : décision qui **reboucle** en arrière |
| « le client fait… **puis** le magasin fait… » | **couloirs** (partitions) : une colonne par acteur |
| un document qui circule (« la facture ») | **nœud d'objet** (rectangle `:Facture`) |

Symboles : ● début · ◉ fin de l'activité · ⊗ fin d'un flot (une branche s'arrête, pas tout).

**Qui choisir ?** **Activité** = un **processus** (souvent multi-acteurs, avec couloirs) · **Séquence** = une **conversation** pour un scénario · **États** = la **vie d'un seul objet**.

### ✏️ Exercice B5 (15 min) — exemple type « commande et livraison »
> « Le client saisit sa commande. Le système vérifie le stock. Si le stock est insuffisant, la commande est refusée. Sinon, en parallèle, le magasin prépare le colis et le service comptable envoie la facture. Quand les deux sont terminés, le transporteur expédie la commande. Tant que le client n'a pas confirmé la réception, le transporteur relance chaque jour. »

**Fais :** diagramme d'activités **avec couloirs** (Client / Système / Magasin / Comptabilité / Transporteur) et l'itération.

---

# Module B6 — Machine à états : la vie d'un objet

| Ce que tu lis | Construction |
|---|---|
| « est **dans l'état** », « **statut** », « **passe de** X **à** Y » | **états** (rectangles arrondis) |
| « **quand** le client valide » | **événement** sur la transition `valider` |
| « **tant qu'elle n'est pas** X », « **seulement si** » | **garde** `[condition]` |
| « **alors** on envoie un mail » | **action** : `événement [garde] / action` |
| « d'abord », « au départ » / « terminé » | état **initial** ● / **final** ◉ |

Syntaxe complète d'une transition : **`événement [garde] / action`**.

### ✏️ Exercice B6 (10 min)
> « Une commande est d'abord dans le panier. Quand le client la valide, elle devient validée et un mail de confirmation est envoyé. Une commande validée peut être annulée tant qu'elle n'est pas expédiée. Une fois livrée, son cycle de vie est terminé. »

---

# Module B7 — Diagramme de déploiement : sur quelles machines ?

Il montre l'architecture **physique** : quels **nœuds** (machines, environnements d'exécution), quels **artefacts** déployés dessus, quels **liens de communication**.

| Élément | Notation |
|---|---|
| **Nœud** matériel | cube 3D, stéréotype `«device»` (PC, serveur, smartphone, carte STM32) |
| **Environnement d'exécution** | cube dans le cube, `«executionEnvironment»` (JVM, Tomcat, navigateur, SGBD) |
| **Artefact** | rectangle `«artifact»` avec un fichier : `app.war`, `api.jar`, `schema.sql` |
| **Chemin de communication** | trait entre nœuds + protocole : `«HTTPS»`, `«JDBC»`, `«TCP/IP»` |
| Multiplicité | `*` sur un lien (« plusieurs postes clients ») |

## Le modèle **trois tiers** standard (dans ton cours)
```
┌───────────────┐   «HTTPS»   ┌────────────────────┐   «JDBC»   ┌─────────────────┐
│ «device»      │ *        1  │ «device»           │ 1       1  │ «device»        │
│ Poste client  │─────────────│ Serveur applicatif │────────────│ Serveur BD      │
│ ┌───────────┐ │             │ ┌────────────────┐ │            │ ┌─────────────┐ │
│ │Navigateur │ │             │ │ Tomcat         │ │            │ │ PostgreSQL  │ │
│ └───────────┘ │             │ │ «artifact»     │ │            │ └─────────────┘ │
└───────────────┘             │ │ journal.war    │ │            └─────────────────┘
   tiers PRÉSENTATION         │ └────────────────┘ │               tiers DONNÉES
                              └────────────────────┘
                                 tiers MÉTIER
```

### ✏️ Exercice B7 (10 min)
Plateforme de covoiturage (Partie C) : appli mobile Android, serveur applicatif Java, base de données, service bancaire externe. Dessine le déploiement avec protocoles et multiplicités.

---

# Module B8 — Bonus (hors cours) : exigences SysML & traçabilité
Pas au programme de M. Hammoudi, mais utile en systèmes embarqués : le diagramme d'exigences **SysML** relie les exigences au modèle.

| Ce que tu lis | Relation |
|---|---|
| X **se décompose en** X.1, X.2 | containment (⊕) |
| découle / **est dérivée** de | «deriveReqt» |
| ce bloc **réalise / satisfait** | «satisfy» |
| ce test **vérifie** | «verify» |
| ce cas d'utilisation **précise** | «refine» |

**Traçabilité :** « cette phrase du client, où est-elle dans mon modèle ? » et « ce composant, à quel besoin sert-il ? ». Une exigence sans lien = oubliée ; un composant sans exigence = inutile.

---
---

# PARTIE C — Synthèse type examen (25 min, tout le pipeline)

> « Bon, je vous explique vite fait : on lance une plateforme de covoiturage pour les étudiants (l'idée est venue d'un pote en soirée). Un conducteur propose des trajets ; un passager — ou voyageur, c'est pareil — réserve des places sur un trajet. Un conducteur peut aussi voyager comme passager. Pour réserver, il faut obligatoirement être connecté. Lors d'une réservation, le passager peut éventuellement laisser un message au conducteur. Pour chaque réservation, on enregistre le nombre de places et le prix payé. Un trajet a une ville de départ, une ville d'arrivée, une date et un nombre de places ; il est ouvert, complet ou annulé. Le paiement passe par un service bancaire externe. L'appli doit être rapide et sécurisée, etc. »

**Fais :** (1) nettoyage + questions · (2) dictionnaire (4 notions, 3 actions) · (3) 2 US par acteur · (4) règles métier + 2 scénarios BDD pour « réserver des places » · (5) cas d'utilisation · (6) diagramme de classes · (7) machine à états d'un Trajet.

---

# PARTIE D — Ta méthode pour le TD « Journal de formation des apprentis »

*Ici pas de corrigé : c'est ton TD. Voici le chemin, question par question.*

**Avant tout (5 min) :** souligne l'énoncé. Tu dois y trouver : **rôles** (noms de personnes-fonctions), **documents** (noms de choses datées), **moments** (mots de temps : « fin de semestre », « début du S7 »), **verbes** (ce que chacun fait).

| Question | Chemin mécanique | Piège à éviter |
|---|---|---|
| **Q1 Acteurs** | 1 rôle humain = 1 acteur. Relis la phrase « limitez-vous à 4 utilisateurs ». Cherche aussi : l'admin « a le même rôle qu'une coordinatrice » → **synonyme**, pas un 5ᵉ acteur. | Ne mets **ni** la plateforme **ni** la base de données comme acteur. |
| **Q2 User stories** | Pour **chaque verbe** rattaché à un rôle dans l'énoncé → 1 US. Puis pour chaque **document** cité (fiche de synthèse, rapport technique, note, blog, soutenance…) → qui le **dépose**, qui le **consulte**, qui l'**évalue** ? | US composées (« créer les journaux **et** saisir les échéances ») → **découpe**. Chaque « afin de » doit dire une **valeur réelle**. |
| **Q3 Règles + BDD** | Pour 3 US par acteur : applique la grille *obligatoire / format / bornes / droits / état / fréquence*. Pense aux **dates** (échéances, périodes), aux **semestres** (S5-S6 vs S7), aux **droits** (qui peut alimenter quel type de document). Puis 1 règle ⇒ 1 scénario OK + 1 scénario KO. | Des tests non observables (« Alors le système est content »). Le **Alors** doit être **visible**. |
| **Q4 Dictionnaire** | Notions = les noms soulignés (journal, entrée, document, promotion, entretien, évaluation, échéance, période de visite…). Actions = les verbes de tes US. Nom informatique court, sans accent. | Oublier de **fusionner** les synonymes (maître d'apprentissage / tuteur entreprise ?) → **pose la question** si tu doutes. |

**Questions à noter pour le client (tu gagnes des points en les posant) :** que contient exactement le « … » dans « note, fiche de synthèse, rapport technique, … » ? Qui peut modifier une entrée déjà déposée ? Que se passe-t-il si une échéance est dépassée ?

---

# 🧠 Fiche réflexe (à garder sous les yeux en TD)

1. **Quoi, pas comment.** Toujours.
2. **Je souligne** : noms (classes/attributs/notions), verbes (actions/cas/opérations), « est un » (héritage), quantités (multiplicités), mots de temps (comportement).
3. **Je fusionne** les synonymes → dictionnaire.
4. **Je signale** les mots flous → question ou hypothèse écrite.
5. **Exigence** : atomique, non ambiguë, vérifiable, correcte, complète, cohérente, évaluée, traçable.
6. **US** : En tant que / je veux / afin de — **1 verbe = 1 US** — INVEST.
7. **Règles** : obligatoire / format / bornes / droits / état / fréquence → **1 règle = 1 scénario OK + 1 KO** (Given/When/Then).
8. **Obligatoire → include**, **optionnel → extend**. Chaque cas important a sa **fiche** (nominal / alternatifs / exceptions).
9. **Héritage ?** est-un / toujours / différence réelle. **Tout-partie ?** durée de vie → ◆, survie/partage → ◇, sinon association.
10. **Processus → activité**, **conversation → séquence**, **vie d'un objet → états**, **machines → déploiement**.
11. **Je vérifie** : chaque phrase utile est tracée **une fois** ; rien n'est inventé « au cas où » ; un diagramme d'objets ne viole aucune multiplicité.

---
---

# ✅ CORRIGÉS (n'ouvre qu'après avoir cherché)

## Corrigé A1
Parties prenantes : usager, bibliothécaire, **direction de la médiathèque** (finance), **service de paiement de la ville**, **DSI de la ville** (hébergement, sécurité), éditeurs/fournisseurs de documents, **CNIL/RGPD** (légal). Non-utilisateurs : direction, DSI, CNIL.
Exigences issues d'elles : DSI → « le système doit fonctionner sur les serveurs de la ville » (contrainte) ; direction → « le système doit produire chaque mois le nombre de prêts par catégorie » (EF).
Techniques : bibliothécaire → **observation** au guichet ; direction → **interview** ; DSI → **lecture de documentation** (normes internes).

## Corrigé A2
**Bruit :** « je suis Mme Durand… depuis 2015 », « refait la peinture », « se plaignent », « moderne ».
**Synonymes :** adhérents = clients = membres → **Adhérent**.
**Flous :** « rapide », « sécurisé », « etc. », « et/ou ». **Solution déguisée :** « gros bouton vert » → besoin : réserver **facilement** (ergonomie).
```
EF1   Le système doit permettre à un adhérent de réserver une place à un cours.
EF2   Le système doit permettre à un adhérent d'annuler une de ses réservations.
EF3   Le système doit permettre au coach de consulter la liste des adhérents inscrits à chacun de ses cours.
ENF1  Le système doit afficher la confirmation d'une réservation en moins de 2 s.   (hypothèse à valider)
ENF2  Seul un utilisateur authentifié doit pouvoir réserver ou annuler.
```
**Questions :** que cache le « etc. » (paiement ? liste d'attente ?) · jusqu'à quand peut-on annuler ? · un cours a-t-il une capacité maximale ? · que veut dire « sécurisé » pour vous ?

## Corrigé A3
| | Qualité violée | Type | Réécriture |
|---|---|---|---|
| a | **Vérifiable** / non ambiguë | ENF ergonomie | « Un nouvel utilisateur doit pouvoir réserver un cours en moins de 3 min sans aide. » |
| b | **Atomique** (3 faits) | EF | 3 exigences : SMS / e-mail / alerte à l'arrivée d'un colis |
| c | indépendante de la solution | **Contrainte** si imposée ; sinon « Le système doit conserver l'historique des commandes. » |
| d | **Vérifiable** | ENF sécurité | « Les données bancaires doivent être chiffrées au stockage et en transit ; seul le service comptable peut les consulter. » |
| e | correcte ✅ (préciser taxes/remises) | EF | — |
| f | **Non ambiguë** (conditionnel « pourrait éventuellement ») + non **évaluée** | EF | « Le système doit afficher l'historique des 12 derniers mois de réservations d'un adhérent. » (priorité à négocier) |
| g | **Cohérente** : contradiction pour un cours à 19h annulé à 10h le jour même | EF | trancher avec le client, puis une seule règle : « annulation possible jusqu'à 2 h avant le début du cours ». |

## Corrigé A4
```
Adhérent  US1 En tant qu'adhérent, je veux réserver une place à un cours afin d'être sûr de pouvoir y participer.
          US2 En tant qu'adhérent, je veux annuler une réservation afin de libérer ma place pour un autre.
          US3 En tant qu'adhérent, je veux consulter le planning de la semaine afin de choisir mes cours.
Coach     US4 En tant que coach, je veux voir la liste des inscrits à mon cours afin de préparer le matériel.
          US5 En tant que coach, je veux signaler l'annulation de mon cours afin que les inscrits soient prévenus.
          US6 En tant que coach, je veux marquer les présents afin de suivre l'assiduité.
Gérant    US7 En tant que gérant, je veux créer un cours afin de l'ouvrir aux réservations.
          US8 En tant que gérant, je veux fixer la capacité d'un cours afin de respecter la taille de la salle.
          US9 En tant que gérant, je veux publier le planning afin que coachs et adhérents le connaissent.
```
INVEST : US6 est la moins **Indépendante** (dépend de US1). Toutes sont testables.
Découpage de l'US composée → US7, US8, US9 (3 verbes = 3 US).

## Corrigé A5
Règles : (R1) l'annulation est possible jusqu'à **2 h** avant le début du cours (hypothèse à valider) · (R2) un adhérent ne peut annuler **que ses propres** réservations · (R3) seule une réservation à l'état **confirmée** peut être annulée · (R4) si une liste d'attente existe, la place libérée est proposée au **premier** de la liste.
```gherkin
Fonctionnalité: Annuler une réservation

  Scénario: annulation dans les délais
    Étant donné que Léa a une réservation confirmée pour le cours de 18h
    Et qu'il est 14h
    Quand Léa annule sa réservation
    Alors la réservation passe à l'état "annulée"
    Et une place se libère dans le cours de 18h

  Scénario: annulation hors délai
    Étant donné que Léa a une réservation confirmée pour le cours de 18h
    Et qu'il est 17h
    Quand Léa annule sa réservation
    Alors le message "Annulation impossible moins de 2 h avant le cours" s'affiche
    Et la réservation reste "confirmée"

  Scénario: liste d'attente
    Étant donné que le cours de 18h est complet et que Tom est premier en liste d'attente
    Quand Léa annule sa réservation à 14h
    Alors Tom reçoit une proposition pour la place libérée
```

## Corrigé A6
| Notion | Définition | Nom informatique |
|---|---|---|
| Usager | personne inscrite qui consulte et emprunte des documents | `Usager` |
| Bibliothécaire | agent qui gère le fonds ; peut agir comme un usager | `Biblio` |
| Document | élément du fonds pouvant être emprunté (livre, DVD…) | `Doc` |
| Prêt | emprunt d'un document par un usager, avec date de retour prévue | `Pret` |
| Pénalité | somme due pour un retour en retard | `Penalite` |

| Action | Définition | Nom informatique |
|---|---|---|
| Consulter le catalogue | rechercher des documents sans être connecté | `ConsultCat` |
| Emprunter un document | enregistrer un prêt pour un usager identifié | `EmpruntDoc` |
| Retourner un document | clôturer un prêt ; déclenche une pénalité si retard | `RetourDoc` |
| Enregistrer un document | ajouter un document au fonds (bibliothécaire) | `EnregDoc` |

Synonyme éliminé (exemple) : « lecteur », « adhérent » → **Usager**.

## Corrigé B1
```
                    ┌──────────────── Système Médiathèque ───────────────┐
  Usager ───────────┼── (Consulter le catalogue)                         │
     △  ────────────┼── (Emprunter un document) ──«include»──► (S'identifier)
     │  ────────────┼── (Retourner un document)                         │
     │              │          ▲                                        │
     │              │          │ «extend» [document en retard]          │
     │              │   (Appliquer une pénalité) ───────────────────────┼─── Système bancaire
Bibliothécaire ─────┼── (Enregistrer un document)                       │     «system»
                    └───────────────────────────────────────────────────┘
```
Déclencheurs : « obligatoirement s'identifier » → include · « si en retard, **peut** » → extend · « tout ce que fait un usager, **et en plus** » → généralisation · « système de paiement de la ville » → acteur externe · « sans être connecté » → **pas** d'include sur Consulter.
```
Cas : Retourner un document
Acteur principal : Usager (ou Bibliothécaire)      Acteur secondaire : Système bancaire (si pénalité)
Précondition  : un prêt en cours existe pour ce document.
Postcondition : le prêt est clôturé ; le document est disponible.
Nominal : 1. L'usager rend le document. 2. Le système retrouve le prêt. 3. Le système vérifie la date.
          4. Le système clôture le prêt et rend le document disponible.
Alternatif : 3a. Retard → le système calcule la pénalité et la fait encaisser via le système bancaire, puis reprend en 4.
Exception  : 2a. Aucun prêt trouvé → le système signale l'anomalie au bibliothécaire. Fin.
```

## Corrigé B2a
| # | Réponse | Mot qui tranche |
|---|---|---|
| 1 | composition ◆ | « composé de » + un appartement n'existe pas sans immeuble |
| 2 | agrégation ◇ | un morceau existe hors playlist, **partagé** |
| 3 | héritage (Salarié, Stagiaire ▷ Personne) | « sont des personnes » |
| 4 | composition ◆ | « comporte » + une ligne sans facture n'a pas de sens |
| 5 | association (Cours * — 1 Enseignant) | « a un… responsable » |
| 6 | héritage, Véhicule **abstrait**, `calculerTaxe()` abstraite | « soit… soit » + « différemment » |
| 7 | énumération `{ EN_ATTENTE, PAYEE, EXPEDIEE }` | liste fermée |
| 8 | **piège → rôle / association** | « **puis** devenir » |
| 9 | agrégation ◇ | « regroupe » + « **réaffectés** » |
| 10 | **piège → attribut / enum** `format` | « **exactement pareil** » |
| 11 | classe d'association `Note` sur Etudiant * — * Matiere | « pour chaque étudiant **et** chaque matière » |
| 12 | association **réflexive** Salarié (chef 0..1 / subordonnés *) | « encadrer d'**autres salariés** » |

## Corrigé B2b
**Nettoyage :** bruit « fondée par deux amis… » ; abonné = client = utilisateur → **Abonné**.
```
Agence  1 ◇────── *  Station  1 ◆────── 1..*  Borne  0..1 ─────── 0..1  Velo  {abstract}
                                                                           △
                                                                  ┌────────┴────────┐
                                                             VeloClassique    VeloElectrique
                                                                              - batterie : int

Abonne  1 ────── *  Location  * ────── 1  Velo
- nom                - heureDepart : DateTime
- type : TypeAbonnement   - heureArrivee : DateTime [0..1]

«enum» TypeAbonnement { MENSUEL, ANNUEL }
```
- Station ◆ Borne : « **n'existe pas en dehors** » → composition.
- Agence ◇ Station : « possède » sans durée de vie → agrégation **ou** association, l'important est de **justifier**.
- Borne 0..1 — 0..1 Velo : « **peut** être garé… **ou** en circulation ».
- Héritage des vélos : « il existe des… » + différence réelle (batterie).
- Location = **vraie classe** (et non classe d'association) car un abonné peut louer **plusieurs fois le même vélo**.
- `heureArrivee [0..1]` : une location en cours n'a pas encore d'heure d'arrivée.

## Corrigé B3
```
gare : Station ──── b1 : Borne ──── v7 : VeloElectrique
            │                          batterie = 45
            └──── b2 : Borne

lea : Abonne ──── loc1 : Location ──── v3 : VeloClassique
                    heureDepart = 8h10
```
Vérifs : Station 1..* Borne ✔ (2) · b2 sans vélo ✔ (0..1) · v3 en circulation, sur aucune borne ✔ · loc1 sans heure d'arrivée ✔ (grâce au `[0..1]`). Sans cette multiplicité, la photo aurait été impossible → le diagramme d'objets a **corrigé** le diagramme de classes.

## Corrigé B4
```
 :Abonne        :Borne           :SystemeCentral
    │ louer()     │                    │
    │────────────▶█ verifierAbonnement(abonne)
    │             █───────────────────▶█
    │             █◀─ ─ ─ ─ valide ─ ─ █
    │    ┌─alt────┼────────────────────┼─────────────────────────┐
    │    │[valide]█ new(abonne, velo)                             │
    │    │        █────────────────────────────────▶ :Location   │
    │    │        █ libererVelo()                                 │
    │    │        █──┐                                            │
    │    │        █◀─┘  (message à soi-même)                      │
    │    ├ ─ ─ ─ ─┼ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┤
    │    │[sinon] █ afficherRefus()                               │
    │    │        █──┐                                            │
    │    │        █◀─┘                                            │
    │    └────────┼───────────────────────────────────────────────┘
```
Communication : `:Abonne —— :Borne —— :SystemeCentral` et `:Borne —— :Location`, messages : `1: louer()` · `1.1: verifierAbonnement()` · `1.2 [valide]: new()` · `1.3 [valide]: libererVelo()` · `1.4 [non valide]: afficherRefus()`.
Opérations déduites : `Borne.louer()`, `Borne.libererVelo()`, `SystemeCentral.verifierAbonnement()`.

## Corrigé B5
```
 Client        │ Système          │ Magasin          │ Comptabilité     │ Transporteur
 ● ─► [Saisir  │                  │                  │                  │
  la commande]─┼─► [Vérifier stock]                  │                  │
               │        ◇         │                  │                  │
               │ [insuffisant]    │                  │                  │
               │  [Refuser] ─► ◉  │                  │                  │
               │ [suffisant]      │                  │                  │
               │   ━━━━ fork ━━━━━┼─► [Préparer      │                  │
               │                  │    le colis] ────┼──────────┐       │
               │                  │                  │ [Envoyer │       │
               │                  │                  │ facture] │       │
               │                  │                  │   ━━━━ join ━━━━━┼─► [Expédier]
               │                  │                  │                  │      │
               │                  │                  │                  │  ◇ ◄─┴──────┐
               │                  │                  │                  │  │[non      │
               │                  │                  │                  │  │confirmé] │
               │                  │                  │                  │  └► [Relancer]
               │                  │                  │                  │ [confirmé] ─► ◉
```
Mots : « si… sinon » → décision · « en parallèle » → fork · « quand les deux » → join · « tant que… relance chaque jour » → décision qui **reboucle** · acteurs multiples → couloirs.

## Corrigé B6
```
 ● ──► [Panier] ──valider / envoyerMailConfirmation──► [Validée] ──expédier──► [Expédiée] ──livrer──► [Livrée] ──► ◉
                                                          │
                                                          └──annuler──► [Annulée] ──► ◉
```
« tant qu'elle n'est pas expédiée » → la transition `annuler` part **seulement** de Validée (la garde est portée par la position de la flèche ; on peut aussi écrire `annuler [non expédiée]`). « et un mail est envoyé » → **action** `/ envoyerMailConfirmation`.

## Corrigé B7
```
┌─────────────────┐ «HTTPS»  ┌──────────────────────┐ «JDBC» ┌───────────────┐
│ «device»        │ *      1 │ «device» Serveur app │ 1    1 │ «device»      │
│ Smartphone      │──────────│ «executionEnv» JVM   │────────│ Serveur BD    │
│ «artifact»      │          │ «artifact» api.jar   │        │ PostgreSQL    │
│ covoit.apk      │          └──────────┬───────────┘        └───────────────┘
└─────────────────┘                     │ «HTTPS» 1
                                        │
                              ┌─────────┴──────────┐
                              │ «device»           │
                              │ Service bancaire   │  (externe)
                              └────────────────────┘
```

## Corrigé Partie C
**Nettoyage :** bruit « vite fait », « un pote en soirée » ; passager = voyageur → **Passager** ; flous « rapide », « sécurisée », « etc. » → questions.
**Dictionnaire :** Trajet (`Trajet`), Réservation (`Resa`), Utilisateur (`Util`, joue conducteur et/ou passager), Statut du trajet (`StatutTrajet`) · Actions : Proposer un trajet (`PropTrajet`), Réserver des places (`ReserverPlaces`), Laisser un message (`LaisserMsg`).
**US :** Conducteur — « …je veux proposer un trajet afin de partager les frais » ; « …je veux annuler mon trajet afin de prévenir les passagers ». Passager — « …je veux réserver des places afin de voyager à moindre coût » ; « …je veux laisser un message au conducteur afin de préciser mon point de rendez-vous ».
**Règles « réserver des places » :** être connecté · nombre de places ≥ 1 et ≤ places restantes · trajet à l'état **ouvert** · on ne réserve pas son propre trajet · paiement accepté par le service bancaire avant confirmation.
```gherkin
Scénario: réservation acceptée
  Étant donné un trajet ouvert Angers → Nantes avec 3 places restantes
  Quand un passager connecté réserve 2 places et que le paiement est accepté
  Alors la réservation est confirmée
  Et il reste 1 place sur le trajet

Scénario: trop de places demandées
  Étant donné un trajet ouvert avec 1 place restante
  Quand un passager connecté demande 2 places
  Alors le message "Places insuffisantes" s'affiche
```
**Cas d'utilisation :** acteurs Passager, Conducteur (▷ Passager : « peut **aussi** voyager comme passager »), Service bancaire. `Réserver des places` —«include»→ `Se connecter` ; `Laisser un message` —«extend»→ `Réserver des places` ; `Proposer un trajet` (Conducteur) ; `Payer` relié au Service bancaire.
**Classes :**
```
Utilisateur  1 ──conducteur── *  Trajet
- nom                              - villeDepart : String
                                   - villeArrivee : String
                                   - date : Date
                                   - nbPlaces : int
                                   - statut : StatutTrajet

Utilisateur  1 ──passager── *  Reservation  * ─────── 1  Trajet
                                - nbPlaces : int
                                - prixPaye : double
                                - message : String [0..1]

«enum» StatutTrajet { OUVERT, COMPLET, ANNULE }
```
**Remarque clé :** conducteur **aussi** passager → **pas** deux sous-classes exclusives : une classe `Utilisateur` qui joue deux **rôles** (piège n°8). En cas d'utilisation, la généralisation d'acteurs reste correcte.
**États d'un Trajet :**
```
 ● ──► [Ouvert] ──toutes places réservées──► [Complet]
          │  ▲                                 │   │
          │  └──── annulation d'une résa ──────┘   │
          └──annuler──► [Annulé] ◄───annuler───────┘
                           │
                           ▼
                           ◉
```
(Correction vs v1 : un trajet **complet** peut aussi être annulé.)

---

### Après ce mini-cours
Refais la **Partie C** dans une semaine, chronométrée à **25 min**, sans les tables. Si un pattern accroche, reviens sur le module concerné. Le jour du TD : **Partie D** + **Fiche réflexe** sous les yeux.
