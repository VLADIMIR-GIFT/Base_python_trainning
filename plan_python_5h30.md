# 🐍 Plan Python — micro-séances de 5h30
*29 septembre → 24 décembre 2026 · 21 notions · 1 séance = 15 min max*

**But final :** arriver en janvier avec des bases **automatiques** pour lire *Build a Large Language Model (from scratch)* — la dernière notion est d'ailleurs un mini-tokenizer, exactement le chapitre 2 du livre.

---

## ⚙️ Les règles du jeu (lis-les une fois)

### Pourquoi c'est construit comme ça
Chaque notion suit **le même moule** :
1. **📖 Cours** (3 min) — une idée + le **chemin de pensée** à suivre.
2. **🧪 Exemple guidé** — un problème résolu pas à pas. Tu le **retapes** toi-même (pas de copier-coller).
3. **✏️ 5 exercices** du **même moule**, avec de petites variations. Si tu as compris le cours, tu réussis. C'est voulu : **5 répétitions = mémoire durable**.

### Le rythme : 1 notion = 3 matins

| Jour | Ce que tu fais | Durée |
|---|---|---|
| **Jour A** | Cours + retaper l'exemple + exercice 1 | ~12 min |
| **Jour B** | Exercices 2 et 3 | ~10 min |
| **Jour C** | Exercices 4 et 5 | ~10 min |

Lundi → vendredi. Le week-end : **rien** (ou rattrapage si tu veux).

### Le rituel de 5h30 (zéro décision à prendre)
```
5h30  lever, eau, lumière
5h35  ouvrir CE fichier à la séance du jour + ouvrir l'éditeur   ← la seule chose à "réussir"
5h37  coder (pas plus de 15 min, même si tu es lancé)
5h52  cocher la case ✅ dans le calendrier — fin
```
**La règle anti-abandon :** la séance est **réussie dès que tu as ouvert le fichier et écrit une ligne**. Un jour « nul » compte quand même. Ce qui tue un plan, ce n'est pas un mauvais jour, c'est le jour **zéro**.

**Si tu rates un jour :** tu reprends **là où tu en étais**, tu **ne doubles jamais**. Le calendrier glisse, ce n'est pas grave.

### Les 3 règles de travail
1. **Essaie 5 min avant d'ouvrir la correction.** Bloqué après 5 min → ouvre, lis, **ferme**, puis retape de mémoire.
2. **Chaque fonction a ses `assert`** (déjà écrits dans les énoncés : ton code doit les faire passer).
3. **Un fichier par notion** : `n01_variables.py`, `n02_conditions.py`… Tu verras ta progression s'empiler.

> 💡 `assert condition` ne fait rien si la condition est vraie, et **plante** si elle est fausse. C'est ton correcteur automatique : si le programme se termine sans erreur, tu as juste.

---

## 📅 Calendrier (coche au fur et à mesure)

| # | Notion | Début (jour A) | A | B | C |
|---|---|---|---|---|---|
| 1 | Variables, types, f-strings | mar 29/09 | ☐ | ☐ | ☐ |
| 2 | Conditions `if / elif / else` | ven 02/10 | ☐ | ☐ | ☐ |
| 3 | Boucle `for` + accumulateur | mer 07/10 | ☐ | ☐ | ☐ |
| 4 | Boucle `while` | lun 12/10 | ☐ | ☐ | ☐ |
| 5 | Fonctions | jeu 15/10 | ☐ | ☐ | ☐ |
| 6 | Chaînes : index & slicing | mar 20/10 | ☐ | ☐ | ☐ |
| 7 | Listes : filtrer & transformer | ven 23/10 | ☐ | ☐ | ☐ |
| 8 | Compréhensions de listes | mer 28/10 | ☐ | ☐ | ☐ |
| 9 | Dictionnaires : le compteur | lun 02/11 | ☐ | ☐ | ☐ |
| 10 | `enumerate`, `zip`, tuples | jeu 05/11 | ☐ | ☐ | ☐ |
| 11 | Ensembles (`set`) | mar 10/11 | ☐ | ☐ | ☐ |
| 12 | Fichiers texte | ven 13/11 | ☐ | ☐ | ☐ |
| 13 | Exceptions | mer 18/11 | ☐ | ☐ | ☐ |
| 14 | Récursivité | lun 23/11 | ☐ | ☐ | ☐ |
| 15 | Classes & objets | jeu 26/11 | ☐ | ☐ | ☐ |
| 16 | Méthodes spéciales (`__len__`…) | mar 01/12 | ☐ | ☐ | ☐ |
| 17 | Héritage | ven 04/12 | ☐ | ☐ | ☐ |
| 18 | `lambda`, `sorted`, `max(key=)` | mer 09/12 | ☐ | ☐ | ☐ |
| 19 | NumPy : tableaux & formes | lun 14/12 | ☐ | ☐ | ☐ |
| 20 | NumPy : calculs & produit matriciel | jeu 17/12 | ☐ | ☐ | ☐ |
| 21 | 🏁 Mini-tokenizer (chapitre 2 du livre) | mar 22/12 | ☐ | ☐ | ☐ |

Les notions 5 → 21 **réutilisent** les précédentes : tu révises sans t'en rendre compte.

---
---

# Notion 1 — Variables, types, f-strings

## 📖 Cours
Une **variable** est une **étiquette** posée sur une valeur : `age = 23`.

| Type | Exemple | Sert à |
|---|---|---|
| `int` | `42` | entiers |
| `float` | `3.14` | décimaux |
| `str` | `"Angers"` | texte |
| `bool` | `True` / `False` | vrai/faux |

**Opérateurs utiles :** `+ - * /` · `//` division **entière** (`17 // 5` → `3`) · `%` **reste** (`17 % 5` → `2`) · `**` puissance.
**Conversions :** `int("42")` → `42` · `str(42)` → `"42"` · `float("3.5")` → `3.5`.
**f-string :** `f"Bonjour {nom}"` insère la variable. `{x:.2f}` = 2 décimales.

**🧭 Chemin de pensée (toujours le même) :**
1. Quelles **données** j'ai ? → une variable chacune.
2. Quel **calcul** ? → une variable pour le résultat.
3. **Afficher** avec une f-string.

## 🧪 Exemple guidé
**Problème :** un article coûte 45,50 € HT, TVA 20 %. Afficher le prix TTC.
```python
# 1. Données
prix_ht = 45.50
tva = 0.20
# 2. Calcul
prix_ttc = prix_ht * (1 + tva)
# 3. Affichage
print(f"Prix TTC : {prix_ttc:.2f} €")   # Prix TTC : 54.60 €
```
Pourquoi `(1 + tva)` ? Parce que TTC = HT + HT×TVA = HT × (1 + TVA). Et `:.2f` évite d'afficher `54.599999`.

## ✏️ Exercices

**Ex 1.1** — Un rectangle mesure 7 × 3. Affiche : `Aire : 21, périmètre : 20`.
<details><summary>Correction</summary>

```python
longueur = 7
largeur = 3
aire = longueur * largeur
perimetre = 2 * (longueur + largeur)
print(f"Aire : {aire}, périmètre : {perimetre}")
```
Même moule : données → calcul → f-string.
</details>

**Ex 1.2** — Convertis 25 °C en Fahrenheit (F = C × 9/5 + 32). Affiche `25°C = 77.0°F`.
<details><summary>Correction</summary>

```python
celsius = 25
fahrenheit = celsius * 9 / 5 + 32
print(f"{celsius}°C = {fahrenheit}°F")
```
`/` donne toujours un `float`, d'où `77.0`.
</details>

**Ex 1.3** — 3725 secondes = combien d'heures, minutes, secondes ? Affiche `1h 2min 5s`. *(indice : `//` et `%`)*
<details><summary>Correction</summary>

```python
total = 3725
heures = total // 3600          # 1
reste = total % 3600            # 125
minutes = reste // 60           # 2
secondes = reste % 60           # 5
print(f"{heures}h {minutes}min {secondes}s")
```
Le couple `//` + `%` = « combien de paquets entiers » + « ce qui reste ». Tu le reverras souvent.
</details>

**Ex 1.4** — On te donne `a = "42"` (texte) et `b = 8`. Affiche leur somme : `50`.
<details><summary>Correction</summary>

```python
a = "42"
b = 8
somme = int(a) + b
print(somme)
```
`"42" + 8` plante (`TypeError`) : on ne mélange pas texte et nombre → on **convertit** d'abord.
</details>

**Ex 1.5** — Notes 12, 15.5 et 9. Affiche `Vladimir a 12.17 de moyenne`.
<details><summary>Correction</summary>

```python
prenom = "Vladimir"
n1, n2, n3 = 12, 15.5, 9
moyenne = (n1 + n2 + n3) / 3
print(f"{prenom} a {moyenne:.2f} de moyenne")
```
Les parenthèses comptent : sans elles, seule `n3` serait divisée par 3.
</details>

---

# Notion 2 — Conditions `if / elif / else`

## 📖 Cours
```python
if condition1:
    ...          # si condition1 vraie
elif condition2:
    ...          # sinon, si condition2 vraie
else:
    ...          # sinon
```
**Comparaisons :** `==` `!=` `<` `<=` `>` `>=` · **Logique :** `and`, `or`, `not`.
Python teste **de haut en bas** et **s'arrête au premier vrai**.

**🧭 Chemin de pensée :**
1. **Liste les cas** possibles sur papier.
2. **Ordonne-les** : du plus **restrictif** au plus large (ex. `>= 16` avant `>= 14`).
3. Teste **les bornes** (la valeur pile sur la limite).

## 🧪 Exemple guidé
**Problème :** afficher la mention d'une note : ≥16 TB, ≥14 B, ≥12 AB, ≥10 Passable, sinon Ajourné.
```python
note = 14
if note >= 16:
    mention = "Très bien"
elif note >= 14:
    mention = "Bien"
elif note >= 12:
    mention = "Assez bien"
elif note >= 10:
    mention = "Passable"
else:
    mention = "Ajourné"
print(mention)   # Bien
```
Si on avait mis `>= 10` en premier, 14 aurait donné « Passable » : **l'ordre est la logique**. Pas besoin d'écrire `14 <= note < 16` : si on arrive au 2ᵉ test, on sait déjà que `note < 16`.

## ✏️ Exercices

**Ex 2.1** — `n = 7`. Affiche `pair` ou `impair`. *(indice : `%`)*
<details><summary>Correction</summary>

```python
n = 7
if n % 2 == 0:
    print("pair")
else:
    print("impair")
```
</details>

**Ex 2.2** — Température `t` : `< 10` → froid, `10` à `24` → doux, `≥ 25` → chaud. Teste avec 9, 10, 24, 25.
<details><summary>Correction</summary>

```python
t = 24
if t < 10:
    print("froid")
elif t < 25:
    print("doux")
else:
    print("chaud")
```
Tester **9, 10, 24, 25** = tester les bornes. C'est là que les bugs se cachent.
</details>

**Ex 2.3** — Cinéma : moins de 12 ans → 5 €, 65 ans et plus → 6 €, sinon 9 €. Un **étudiant** au tarif 9 € a 2 € de réduction. Variables : `age = 22`, `etudiant = True` → `7`.
<details><summary>Correction</summary>

```python
age = 22
etudiant = True
if age < 12:
    prix = 5
elif age >= 65:
    prix = 6
else:
    prix = 9
    if etudiant:
        prix = prix - 2
print(prix)   # 7
```
La variation : un `if` **dans** le `else`, car la réduction ne concerne que ce cas.
</details>

**Ex 2.4** — Année bissextile : divisible par 4 **et** (pas par 100 **ou** par 400). Vérifie : 2024 oui, 1900 non, 2000 oui.
<details><summary>Correction</summary>

```python
annee = 1900
if annee % 4 == 0 and (annee % 100 != 0 or annee % 400 == 0):
    print("bissextile")
else:
    print("non bissextile")
```
Les parenthèses traduisent exactement le « et (… ou …) » de l'énoncé.
</details>

**Ex 2.5** — Radar, limite 80 : `v ≤ 80` → OK ; `v ≤ 100` → amende ; au-delà → retrait de permis.
<details><summary>Correction</summary>

```python
limite = 80
v = 95
if v <= limite:
    print("OK")
elif v <= limite + 20:
    print("amende")
else:
    print("retrait de permis")
```
</details>

---

# Notion 3 — Boucle `for` + le pattern accumulateur

## 📖 Cours
```python
for i in range(1, 6):     # i vaut 1, 2, 3, 4, 5  (6 EXCLU)
    print(i)
```
`range(fin)` → 0 à fin-1 · `range(debut, fin)` · `range(debut, fin, pas)`.

**Le pattern le plus important de la programmation — l'accumulateur :**
```python
total = 0                 # 1. INITIALISER (0 pour une somme, 1 pour un produit)
for x in ...:             # 2. PARCOURIR
    total = total + x     # 3. METTRE À JOUR  (ou total += x)
print(total)              # 4. UTILISER après la boucle
```
**🧭 Chemin de pensée :** Qu'est-ce que j'accumule ? → valeur de départ ? → quoi ajouter à chaque tour ?

## 🧪 Exemple guidé
**Problème :** somme des carrés de 1 à 10.
```python
total = 0
for i in range(1, 11):    # 11 pour inclure 10
    total += i ** 2
print(total)              # 385
```
Tour 1 : total = 0 + 1 = 1 · tour 2 : 1 + 4 = 5 · tour 3 : 5 + 9 = 14… Fais les 3 premiers tours **à la main** une fois : c'est ce qui construit l'intuition.

## ✏️ Exercices

**Ex 3.1** — Somme de 1 à 100. Doit afficher `5050`.
<details><summary>Correction</summary>

```python
total = 0
for i in range(1, 101):
    total += i
print(total)
```
</details>

**Ex 3.2** — Factorielle de 6 (1×2×3×4×5×6). Doit afficher `720`.
<details><summary>Correction</summary>

```python
produit = 1          # pas 0 ! sinon tout vaut 0
for i in range(1, 7):
    produit *= i
print(produit)
```
La variation : un **produit** s'initialise à **1**.
</details>

**Ex 3.3** — Combien de multiples de 7 entre 1 et 100 ? → `14`.
<details><summary>Correction</summary>

```python
compteur = 0
for i in range(1, 101):
    if i % 7 == 0:
        compteur += 1
print(compteur)
```
Un **compteur** est un accumulateur qui ajoute 1 **seulement si** une condition est vraie.
</details>

**Ex 3.4** — Affiche la table de 9 : `9 x 1 = 9` … `9 x 10 = 90`.
<details><summary>Correction</summary>

```python
for i in range(1, 11):
    print(f"9 x {i} = {9 * i}")
```
</details>

**Ex 3.5** — FizzBuzz de 1 à 20 : multiple de 3 → `Fizz`, de 5 → `Buzz`, des deux → `FizzBuzz`, sinon le nombre.
<details><summary>Correction</summary>

```python
for i in range(1, 21):
    if i % 15 == 0:          # le cas le plus restrictif D'ABORD (notion 2)
        print("FizzBuzz")
    elif i % 3 == 0:
        print("Fizz")
    elif i % 5 == 0:
        print("Buzz")
    else:
        print(i)
```
</details>

---

# Notion 4 — Boucle `while`

## 📖 Cours
`for` = je sais **combien** de tours. `while` = je répète **tant qu'une condition est vraie** (je ne sais pas combien de tours).
```python
n = 1                 # 1. INITIALISER
while n < 100:        # 2. CONDITION
    n = n * 2         # 3. PROGRESSER  ← sans ça : boucle infinie
print(n)              # 128
```
**🧭 Chemin de pensée :** Quand est-ce que je **m'arrête** ? → écris la condition **inverse** dans le `while` (« je m'arrête quand n ≥ 100 » → `while n < 100`). Puis : qu'est-ce qui **change** à chaque tour ?

Astuce pour les chiffres d'un nombre : `n % 10` = dernier chiffre, `n // 10` = le nombre sans son dernier chiffre.

## 🧪 Exemple guidé
**Problème :** 1000 € placés à 5 %/an. Combien d'années pour dépasser 2000 € ?
```python
capital = 1000
annees = 0
while capital < 2000:        # je m'arrête quand capital >= 2000
    capital *= 1.05
    annees += 1              # compteur de tours
print(annees)                # 15
```
On combine deux choses déjà vues : une **condition d'arrêt** et un **compteur**.

## ✏️ Exercices

**Ex 4.1** — Divise 1000 par 2 tant qu'il est > 1. Combien de divisions ? → `10`.
<details><summary>Correction</summary>

```python
n = 1000
etapes = 0
while n > 1:
    n = n / 2
    etapes += 1
print(etapes)
```
</details>

**Ex 4.2** — Somme des chiffres de 4827 → `21`.
<details><summary>Correction</summary>

```python
n = 4827
somme = 0
while n > 0:
    somme += n % 10    # dernier chiffre
    n = n // 10        # on l'enlève
print(somme)
```
</details>

**Ex 4.3** — Plus petit entier `n` tel que `n²` > 500 → `23`.
<details><summary>Correction</summary>

```python
n = 1
while n ** 2 <= 500:   # je continue tant que ce n'est PAS encore > 500
    n += 1
print(n)
```
Condition d'arrêt « n² > 500 » → condition du while : son **inverse** `n² <= 500`.
</details>

**Ex 4.4** — Suite de Syracuse depuis 6 : si pair → n/2, sinon → 3n+1. Combien d'étapes pour atteindre 1 ? → `8`.
<details><summary>Correction</summary>

```python
n = 6
etapes = 0
while n != 1:
    if n % 2 == 0:
        n = n // 2
    else:
        n = 3 * n + 1
    etapes += 1
print(etapes)   # 6→3→10→5→16→8→4→2→1
```
</details>

**Ex 4.5** — Tu as 120 € et épargnes 50 €/mois. Combien de mois pour atteindre au moins 1000 € ? → `18`.
<details><summary>Correction</summary>

```python
epargne = 120
mois = 0
while epargne < 1000:
    epargne += 50
    mois += 1
print(mois)
```
Exactement le moule de l'exemple guidé, avec une addition au lieu d'une multiplication.
</details>

---

# Notion 5 — Fonctions

## 📖 Cours
Une fonction = **une tâche avec un nom**. Elle **reçoit** des paramètres et **renvoie** un résultat.
```python
def ttc(prix_ht, taux=0.20):      # taux a une valeur par DÉFAUT
    return round(prix_ht * (1 + taux), 2)

print(ttc(100))        # 120.0
print(ttc(100, 0.055)) # 105.5
```
⚠️ **`return` ≠ `print`** : `print` affiche et c'est perdu ; `return` **rend** la valeur pour qu'on la réutilise. Une fonction sans `return` renvoie `None`.

**🧭 Chemin de pensée (5 étapes) :**
1. **Nom** = un verbe (`calculer_moyenne`).
2. **Entrées** = les paramètres.
3. **Sortie** = ce que je `return`.
4. **Corps** = le calcul (souvent un pattern déjà vu !).
5. **Tests** = 2-3 `assert`.

## 🧪 Exemple guidé
**Problème :** transformer l'exercice 2.1 (pair/impair) en fonction réutilisable.
```python
def est_pair(n):
    return n % 2 == 0      # l'expression vaut déjà True ou False

assert est_pair(4) == True
assert est_pair(7) == False
assert est_pair(0) == True
print("OK")
```
Pas besoin de `if … return True else return False` : la comparaison **est** déjà un booléen.

## ✏️ Exercices

**Ex 5.1** — `aire_cercle(r)` avec π ≈ 3.14159. Doit passer : `assert round(aire_cercle(1), 2) == 3.14` et `assert round(aire_cercle(2), 2) == 12.57`.
<details><summary>Correction</summary>

```python
def aire_cercle(r):
    return 3.14159 * r ** 2

assert round(aire_cercle(1), 2) == 3.14
assert round(aire_cercle(2), 2) == 12.57
```
</details>

**Ex 5.2** — `maximum(a, b, c)` **sans** `max()`. Tests : `maximum(3, 9, 5) == 9`, `maximum(-1, -5, -2) == -1`.
<details><summary>Correction</summary>

```python
def maximum(a, b, c):
    plus_grand = a
    if b > plus_grand:
        plus_grand = b
    if c > plus_grand:
        plus_grand = c
    return plus_grand

assert maximum(3, 9, 5) == 9
assert maximum(-1, -5, -2) == -1
```
Pattern « meilleur candidat » : je suppose que le 1ᵉʳ est le meilleur, puis je le remplace si je trouve mieux.
</details>

**Ex 5.3** — `mention(note)` qui **renvoie** la mention (reprends l'exemple de la notion 2). Tests : `mention(14) == "Bien"`, `mention(9.5) == "Ajourné"`.
<details><summary>Correction</summary>

```python
def mention(note):
    if note >= 16:
        return "Très bien"
    elif note >= 14:
        return "Bien"
    elif note >= 12:
        return "Assez bien"
    elif note >= 10:
        return "Passable"
    return "Ajourné"

assert mention(14) == "Bien"
assert mention(9.5) == "Ajourné"
assert mention(16) == "Très bien"
```
`return` **sort** de la fonction : pas besoin de `else` final.
</details>

**Ex 5.4** — `somme_jusqu_a(n)` = 1 + 2 + … + n. Tests : `somme_jusqu_a(100) == 5050`, `somme_jusqu_a(1) == 1`.
<details><summary>Correction</summary>

```python
def somme_jusqu_a(n):
    total = 0
    for i in range(1, n + 1):
        total += i
    return total

assert somme_jusqu_a(100) == 5050
assert somme_jusqu_a(1) == 1
```
C'est l'Ex 3.1 « emballé » : une fonction, c'est souvent un pattern connu avec un nom.
</details>

**Ex 5.5** — `puissance(base, exp=2)` **sans** `**`, avec une boucle. Tests : `puissance(3) == 9`, `puissance(2, 10) == 1024`, `puissance(5, 0) == 1`.
<details><summary>Correction</summary>

```python
def puissance(base, exp=2):
    resultat = 1
    for _ in range(exp):      # _ : variable dont on ne se sert pas
        resultat *= base
    return resultat

assert puissance(3) == 9
assert puissance(2, 10) == 1024
assert puissance(5, 0) == 1
```
</details>

---

# Notion 6 — Chaînes : indexation & slicing

## 📖 Cours
```
 s =   "P  y  t  h  o  n"
 index  0  1  2  3  4  5
 négatif-6 -5 -4 -3 -2 -1
```
- `s[0]` → `"P"` · `s[-1]` → `"n"` (dernier)
- `s[1:4]` → `"yth"` (**début inclus, fin exclue**)
- `s[:2]` → `"Py"` · `s[2:]` → `"thon"` · `s[::-1]` → `"nohtyP"` (inversé)
- `len(s)` → 6

**Méthodes utiles :** `.lower()` `.upper()` `.strip()` (enlève espaces aux bords) `.replace(a, b)` `.split()` (coupe en liste de mots) `.count(x)` `.index(x)` (position de x).
Une chaîne est **immuable** : on ne la modifie pas, on en **crée** une nouvelle.

**🧭 Chemin de pensée :** dessine les index sous le mot, puis demande-toi : je veux **un** caractère (`[i]`) ou **un morceau** (`[a:b]`) ?

## 🧪 Exemple guidé
**Problème :** initiales de `"jean vladimir houeto"` → `"JVH"`.
```python
def initiales(nom_complet):
    resultat = ""                          # accumulateur de TEXTE
    for mot in nom_complet.split():        # ["jean", "vladimir", "houeto"]
        resultat += mot[0].upper()
    return resultat

assert initiales("jean vladimir houeto") == "JVH"
```
L'accumulateur de la notion 3 marche aussi avec du texte : on part de `""` et on **concatène**.

## ✏️ Exercices

**Ex 6.1** — `premier_dernier(s)` renvoie 1ᵉʳ + dernier caractère. Test : `premier_dernier("Python") == "Pn"`.
<details><summary>Correction</summary>

```python
def premier_dernier(s):
    return s[0] + s[-1]

assert premier_dernier("Python") == "Pn"
```
</details>

**Ex 6.2** — `inverse(s)`. Test : `inverse("ESEO") == "OESE"`.
<details><summary>Correction</summary>

```python
def inverse(s):
    return s[::-1]

assert inverse("ESEO") == "OESE"
```
</details>

**Ex 6.3** — `est_palindrome(s)` sans tenir compte des majuscules. Tests : `"Kayak"` → `True`, `"Java"` → `False`.
<details><summary>Correction</summary>

```python
def est_palindrome(s):
    s = s.lower()
    return s == s[::-1]

assert est_palindrome("Kayak") == True
assert est_palindrome("Java") == False
```
Combinaison de 6.2 et d'une comparaison booléenne (exemple de la notion 5).
</details>

**Ex 6.4** — `compte_voyelles(s)` (voyelles : `aeiouy`, majuscules comprises). Test : `compte_voyelles("Bonjour Angers") == 5`.
<details><summary>Correction</summary>

```python
def compte_voyelles(s):
    compteur = 0
    for c in s.lower():
        if c in "aeiouy":
            compteur += 1
    return compteur

assert compte_voyelles("Bonjour Angers") == 5   # o, o, u, a, e
```
`c in "aeiouy"` : `in` teste si un caractère est **dans** une chaîne.
</details>

**Ex 6.5** — `masque_email(e)` garde la 1ʳᵉ lettre, remplace le reste avant `@` par `*`. Test : `masque_email("vladimir@eseo.fr") == "v*******@eseo.fr"`.
<details><summary>Correction</summary>

```python
def masque_email(e):
    i = e.index("@")                 # position du @ : 8
    return e[0] + "*" * (i - 1) + e[i:]

assert masque_email("vladimir@eseo.fr") == "v*******@eseo.fr"
```
`"*" * 7` → `"*******"` : multiplier une chaîne la **répète**.
</details>

---

# Notion 7 — Listes : filtrer & transformer

## 📖 Cours
```python
notes = [12, 8, 15]
notes.append(10)       # ajoute à la fin → [12, 8, 15, 10]
notes[0]               # 12
len(notes)             # 4
8 in notes             # True
sum(notes), min(notes), max(notes)
sorted(notes)          # NOUVELLE liste triée ; notes.sort() trie SUR PLACE
```
**Les 2 patterns de liste (à connaître par cœur) :**
```python
# FILTRER : garder certains éléments          # TRANSFORMER : modifier chaque élément
resultat = []                                  resultat = []
for x in liste:                                for x in liste:
    if condition(x):                               resultat.append(f(x))
        resultat.append(x)
```
**🧭 Chemin de pensée :** je **garde** certains éléments (filtrer) ou je les **change tous** (transformer) ? Puis je remplis le moule.

## 🧪 Exemple guidé
**Problème :** garder les notes ≥ 10.
```python
def admises(notes):
    resultat = []
    for n in notes:
        if n >= 10:
            resultat.append(n)
    return resultat

assert admises([8, 12, 15, 9, 10]) == [12, 15, 10]
assert admises([]) == []
```
C'est un **accumulateur de liste** : on part de `[]` au lieu de `0`, et on fait `append` au lieu de `+=`.

## ✏️ Exercices

**Ex 7.1** — `positifs(lst)` garde les nombres > 0. Test : `positifs([-2, 5, 0, 3]) == [5, 3]`.
<details><summary>Correction</summary>

```python
def positifs(lst):
    resultat = []
    for x in lst:
        if x > 0:
            resultat.append(x)
    return resultat

assert positifs([-2, 5, 0, 3]) == [5, 3]
```
</details>

**Ex 7.2** — `doubles(lst)` multiplie chaque élément par 2. Test : `doubles([1, 4, 7]) == [2, 8, 14]`.
<details><summary>Correction</summary>

```python
def doubles(lst):
    resultat = []
    for x in lst:
        resultat.append(x * 2)
    return resultat

assert doubles([1, 4, 7]) == [2, 8, 14]
```
Pattern **transformer**.
</details>

**Ex 7.3** — `moyenne(lst)`, renvoie `0` si la liste est vide. Tests : `moyenne([10, 14]) == 12`, `moyenne([]) == 0`.
<details><summary>Correction</summary>

```python
def moyenne(lst):
    if len(lst) == 0:
        return 0            # on traite le cas piège AVANT (sinon division par 0)
    return sum(lst) / len(lst)

assert moyenne([10, 14]) == 12
assert moyenne([]) == 0
```
</details>

**Ex 7.4** — `plus_grand(lst)` **sans** `max()`. Test : `plus_grand([3, 17, 8]) == 17`.
<details><summary>Correction</summary>

```python
def plus_grand(lst):
    meilleur = lst[0]
    for x in lst:
        if x > meilleur:
            meilleur = x
    return meilleur

assert plus_grand([3, 17, 8]) == 17
assert plus_grand([-4, -1, -9]) == -1
```
Le pattern « meilleur candidat » de l'Ex 5.2, sur une liste.
</details>

**Ex 7.5** — `mots_longs(texte, n)` garde les mots de plus de `n` lettres. Test : `mots_longs("le modèle apprend vite", 4) == ["modèle", "apprend"]`.
<details><summary>Correction</summary>

```python
def mots_longs(texte, n):
    resultat = []
    for mot in texte.split():
        if len(mot) > n:
            resultat.append(mot)
    return resultat

assert mots_longs("le modèle apprend vite", 4) == ["modèle", "apprend"]
```
Filtrer + `split()` (notion 6).
</details>

---

# Notion 8 — Compréhensions de listes

## 📖 Cours
Les deux patterns de la notion 7 tiennent **en une ligne** :
```python
[f(x) for x in liste]                 # TRANSFORMER
[x for x in liste if condition(x)]    # FILTRER
[f(x) for x in liste if condition(x)] # les deux
```
**🧭 Traduction mécanique** (boucle → compréhension) :
```python
resultat = []                     →   resultat = [ x*2   for x in lst   if x > 0 ]
for x in lst:          ───────────────────────────┘        │               │
    if x > 0:          ────────────────────────────────────────────────────┘
        resultat.append(x*2)   ───────────────┘ (ce qu'on append va DEVANT)
```
Méthodes de texte utiles ici : `.isupper()` (majuscule ?), `.isdigit()` (chiffre ?).

## 🧪 Exemple guidé
**Problème :** réécrire `admises` (notion 7) en une ligne.
```python
def admises(notes):
    return [n for n in notes if n >= 10]

assert admises([8, 12, 15, 9, 10]) == [12, 15, 10]
```
Lis-la à voix haute : « **n**, pour chaque **n** dans **notes**, si **n ≥ 10** ».

## ✏️ Exercices

**Ex 8.1** — Liste des carrés de 1 à 10. Test : le résultat vaut `[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`.
<details><summary>Correction</summary>

```python
carres = [i ** 2 for i in range(1, 11)]
assert carres == [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
</details>

**Ex 8.2** — Nombres pairs de 0 à 20 (avec un `if`). Test : `len(pairs) == 11`.
<details><summary>Correction</summary>

```python
pairs = [i for i in range(21) if i % 2 == 0]
assert len(pairs) == 11
```
</details>

**Ex 8.3** — Longueur de chaque mot de `"je code chaque matin"`. Test : `[2, 4, 6, 5]`.
<details><summary>Correction</summary>

```python
phrase = "je code chaque matin"
longueurs = [len(m) for m in phrase.split()]
assert longueurs == [2, 4, 6, 5]
```
</details>

**Ex 8.4** — Convertis `["12", "7", "30"]` en entiers. Test : `[12, 7, 30]`.
<details><summary>Correction</summary>

```python
textes = ["12", "7", "30"]
nombres = [int(t) for t in textes]
assert nombres == [12, 7, 30]
```
</details>

**Ex 8.5** — Mots qui commencent par une majuscule dans `"Vladimir travaille chez TBMaestro depuis Angers"`. Test : `["Vladimir", "TBMaestro", "Angers"]`.
<details><summary>Correction</summary>

```python
phrase = "Vladimir travaille chez TBMaestro depuis Angers"
noms = [m for m in phrase.split() if m[0].isupper()]
assert noms == ["Vladimir", "TBMaestro", "Angers"]
```
</details>

---

# Notion 9 — Dictionnaires : le pattern compteur

## 📖 Cours
Un dictionnaire associe une **clé** à une **valeur** : `ages = {"Léa": 21, "Tom": 23}`.
```python
ages["Léa"]            # 21
ages["Max"] = 19       # ajoute ou modifie
"Tom" in ages          # True (teste les CLÉS)
ages.get("Zoé", 0)     # 0 : valeur par défaut si la clé n'existe pas (pas d'erreur)
for cle, valeur in ages.items():
    ...
```
**Le pattern compteur (le plus utile en data et en NLP) :**
```python
compte = {}
for x in elements:
    compte[x] = compte.get(x, 0) + 1
```
**Variante « dictionnaire de listes »** (grouper) :
```python
groupes = {}
for x in elements:
    cle = ...
    if cle not in groupes:
        groupes[cle] = []
    groupes[cle].append(x)
```
**🧭 Chemin de pensée :** qu'est-ce qui est la **clé** (ce que je cherche) ? qu'est-ce qui est la **valeur** (ce que j'en sais) ?

## 🧪 Exemple guidé
**Problème :** fréquence des lettres de `"banane"`.
```python
def frequences(texte):
    compte = {}
    for c in texte:
        compte[c] = compte.get(c, 0) + 1
    return compte

assert frequences("banane") == {"b": 1, "a": 2, "n": 2, "e": 1}
```
Au 1ᵉʳ `"a"`, `get` renvoie 0 → on stocke 1. Au 2ᵉ `"a"`, `get` renvoie 1 → on stocke 2.

## ✏️ Exercices

**Ex 9.1** — `freq_mots(texte)` compte les **mots**. Test : `freq_mots("le chat et le chien et le rat")["le"] == 3`.
<details><summary>Correction</summary>

```python
def freq_mots(texte):
    compte = {}
    for mot in texte.split():
        compte[mot] = compte.get(mot, 0) + 1
    return compte

d = freq_mots("le chat et le chien et le rat")
assert d["le"] == 3 and d["et"] == 2 and d["rat"] == 1
```
Seule différence avec l'exemple : `.split()`.
</details>

**Ex 9.2** — `plus_frequent(d)` renvoie la clé qui a la plus grande valeur. Test : `plus_frequent({"a": 2, "b": 5, "c": 1}) == "b"`.
<details><summary>Correction</summary>

```python
def plus_frequent(d):
    meilleure_cle = None
    meilleure_val = -1
    for cle, val in d.items():
        if val > meilleure_val:
            meilleure_cle = cle
            meilleure_val = val
    return meilleure_cle

assert plus_frequent({"a": 2, "b": 5, "c": 1}) == "b"
```
« Meilleur candidat » (Ex 7.4), mais on retient **deux** choses : la clé et sa valeur.
</details>

**Ex 9.3** — `telephone(annuaire, nom)` renvoie le numéro ou `"inconnu"`. Test avec `{"Léa": "0601"}` : `telephone(a, "Léa") == "0601"`, `telephone(a, "Tom") == "inconnu"`.
<details><summary>Correction</summary>

```python
def telephone(annuaire, nom):
    return annuaire.get(nom, "inconnu")

a = {"Léa": "0601"}
assert telephone(a, "Léa") == "0601"
assert telephone(a, "Tom") == "inconnu"
```
</details>

**Ex 9.4** — `grouper(mots)` regroupe par première lettre. Test : `grouper(["chat", "rat", "chien"]) == {"c": ["chat", "chien"], "r": ["rat"]}`.
<details><summary>Correction</summary>

```python
def grouper(mots):
    groupes = {}
    for mot in mots:
        cle = mot[0]
        if cle not in groupes:
            groupes[cle] = []
        groupes[cle].append(mot)
    return groupes

assert grouper(["chat", "rat", "chien"]) == {"c": ["chat", "chien"], "r": ["rat"]}
```
</details>

**Ex 9.5** — `inverser(d)` échange clés et valeurs. Test : `inverser({"a": 1, "b": 2}) == {1: "a", 2: "b"}`.
<details><summary>Correction</summary>

```python
def inverser(d):
    resultat = {}
    for cle, val in d.items():
        resultat[val] = cle
    return resultat

assert inverser({"a": 1, "b": 2}) == {1: "a", 2: "b"}
```
Garde-la en tête : c'est **exactement** ce qu'il faudra pour décoder des tokens (notion 21).
</details>

---

# Notion 10 — `enumerate`, `zip`, tuples

## 📖 Cours
**Tuple** = liste **non modifiable** : `point = (3, 4)`. **Unpacking** : `x, y = point`.
Échanger deux variables : `a, b = b, a`. Une fonction peut renvoyer plusieurs valeurs : `return mini, maxi`.

```python
for i, x in enumerate(["a", "b"]):        # i = index, x = valeur → (0,"a"), (1,"b")
for a, b in zip([1, 2], [10, 20]):        # parcourt 2 listes EN MÊME TEMPS → (1,10), (2,20)
```
**🧭 Chemin de pensée :** j'ai besoin de la **position** ? → `enumerate`. J'ai **deux listes alignées** ? → `zip`.

## 🧪 Exemple guidé
**Problème :** afficher un classement numéroté à partir de 1.
```python
eleves = ["Alice", "Bob", "Chloé"]
for rang, nom in enumerate(eleves, start=1):
    print(f"{rang}. {nom}")
# 1. Alice
# 2. Bob
# 3. Chloé
```
Sans `enumerate`, il faudrait gérer un compteur à la main : `enumerate` le fait pour toi.

## ✏️ Exercices

**Ex 10.1** — `min_max(lst)` renvoie le tuple `(min, max)`. Test : `mini, maxi = min_max([4, 1, 9])` puis `mini == 1 and maxi == 9`.
<details><summary>Correction</summary>

```python
def min_max(lst):
    return min(lst), max(lst)

mini, maxi = min_max([4, 1, 9])
assert mini == 1 and maxi == 9
```
</details>

**Ex 10.2** — `indices_de(lst, val)` renvoie toutes les positions de `val`. Test : `indices_de([3, 7, 3, 1, 3], 3) == [0, 2, 4]`.
<details><summary>Correction</summary>

```python
def indices_de(lst, val):
    return [i for i, x in enumerate(lst) if x == val]

assert indices_de([3, 7, 3, 1, 3], 3) == [0, 2, 4]
```
Compréhension (notion 8) + `enumerate`.
</details>

**Ex 10.3** — `produit_scalaire(u, v)` = somme des produits terme à terme. Test : `produit_scalaire([1, 2, 3], [4, 5, 6]) == 32`.
<details><summary>Correction</summary>

```python
def produit_scalaire(u, v):
    total = 0
    for a, b in zip(u, v):
        total += a * b
    return total

assert produit_scalaire([1, 2, 3], [4, 5, 6]) == 32   # 4 + 10 + 18
```
⭐ C'est **l'opération de base** de l'attention dans un LLM. Tu la reverras en NumPy (notion 20).
</details>

**Ex 10.4** — Construis un dict `nom → note` à partir de `noms = ["Léa", "Tom"]` et `notes = [15, 12]`. Test : `{"Léa": 15, "Tom": 12}`.
<details><summary>Correction</summary>

```python
noms = ["Léa", "Tom"]
notes = [15, 12]
d = {}
for nom, note in zip(noms, notes):
    d[nom] = note
assert d == {"Léa": 15, "Tom": 12}
# version courte : d = dict(zip(noms, notes))
```
</details>

**Ex 10.5** — `ecarts(lst)` = différences entre éléments consécutifs. Test : `ecarts([1, 4, 9, 16]) == [3, 5, 7]`. *(indice : `zip(lst, lst[1:])`)*
<details><summary>Correction</summary>

```python
def ecarts(lst):
    return [b - a for a, b in zip(lst, lst[1:])]

assert ecarts([1, 4, 9, 16]) == [3, 5, 7]
```
`zip(lst, lst[1:])` donne les **paires voisines** : (1,4), (4,9), (9,16). Astuce très utilisée.
</details>

---

# Notion 11 — Ensembles (`set`)

## 📖 Cours
Un `set` = collection **sans doublons** et **sans ordre**.
```python
s = set([3, 1, 3, 2])     # {1, 2, 3}
s.add(5)
3 in s                    # très rapide, même sur des millions d'éléments
a & b    # intersection (dans les deux)
a | b    # union (dans l'un ou l'autre)
a - b    # différence (dans a mais pas dans b)
len(set(lst))             # nombre d'éléments DISTINCTS
```
**🧭 Chemin de pensée :** la question contient « **distinct** », « **unique** », « **commun** », « **déjà vu** » → pense `set`.

## 🧪 Exemple guidé
**Problème :** une liste contient-elle des doublons ?
```python
def a_des_doublons(lst):
    return len(set(lst)) != len(lst)

assert a_des_doublons([1, 2, 3, 2]) == True
assert a_des_doublons([1, 2, 3]) == False
```
Si le `set` est plus petit que la liste, c'est que des éléments ont été **fusionnés** → il y avait des doublons.

## ✏️ Exercices

**Ex 11.1** — `nb_mots_distincts(texte)`. Test : `nb_mots_distincts("un deux un trois deux") == 3`.
<details><summary>Correction</summary>

```python
def nb_mots_distincts(texte):
    return len(set(texte.split()))

assert nb_mots_distincts("un deux un trois deux") == 3
```
</details>

**Ex 11.2** — `lettres_communes(m1, m2)`. Test : `lettres_communes("maison", "raison") == {"a", "i", "s", "o", "n"}`.
<details><summary>Correction</summary>

```python
def lettres_communes(m1, m2):
    return set(m1) & set(m2)

assert lettres_communes("maison", "raison") == {"a", "i", "s", "o", "n"}
```
</details>

**Ex 11.3** — Inscrits en maths mais **pas** en info. `maths = {"Léa", "Tom", "Max"}`, `info = {"Tom"}` → `{"Léa", "Max"}`.
<details><summary>Correction</summary>

```python
maths = {"Léa", "Tom", "Max"}
info = {"Tom"}
assert maths - info == {"Léa", "Max"}
```
</details>

**Ex 11.4** — `premier_doublon(lst)` renvoie le premier élément déjà vu, sinon `None`. Test : `premier_doublon([3, 1, 4, 1, 5, 3]) == 1`.
<details><summary>Correction</summary>

```python
def premier_doublon(lst):
    vus = set()
    for x in lst:
        if x in vus:
            return x
        vus.add(x)
    return None

assert premier_doublon([3, 1, 4, 1, 5, 3]) == 1
assert premier_doublon([1, 2]) is None
```
Le set sert de **mémoire** « déjà vu ».
</details>

**Ex 11.5** — `vocabulaire(texte)` : liste **triée** des mots uniques, en minuscules. Test : `vocabulaire("Le chat voit le chien") == ["chat", "chien", "le", "voit"]`.
<details><summary>Correction</summary>

```python
def vocabulaire(texte):
    return sorted(set(texte.lower().split()))

assert vocabulaire("Le chat voit le chien") == ["chat", "chien", "le", "voit"]
```
⭐ C'est la **première étape d'un tokenizer** : construire le vocabulaire (notion 21).
</details>

---

# Notion 12 — Fichiers texte

## 📖 Cours
```python
# ÉCRIRE ("w" écrase, "a" ajoute à la fin)
with open("notes.txt", "w", encoding="utf-8") as f:
    f.write("première ligne\n")        # \n = retour à la ligne

# LIRE ligne par ligne
with open("notes.txt", "r", encoding="utf-8") as f:
    for ligne in f:
        ligne = ligne.strip()           # enlève le \n de fin
```
`with` **ferme** le fichier tout seul, même en cas d'erreur. Toujours `encoding="utf-8"` (sinon les accents cassent).

**🧭 Chemin de pensée :** **ouvrir** → **parcourir** les lignes → **nettoyer** (`strip`, `split`) → **traiter** (un pattern déjà connu : accumulateur, compteur…).

## 🧪 Exemple guidé
**Problème :** écrire 3 lignes dans un fichier, puis compter ses lignes.
```python
with open("journal.txt", "w", encoding="utf-8") as f:
    f.write("lundi : notion 1\n")
    f.write("mardi : notion 1\n")
    f.write("mercredi : notion 2\n")

nb = 0
with open("journal.txt", "r", encoding="utf-8") as f:
    for ligne in f:
        nb += 1                 # un compteur (notion 3) !
assert nb == 3
```

## ✏️ Exercices

**Ex 12.1** — Écris les nombres 1 à 10, un par ligne, dans `nombres.txt`.
<details><summary>Correction</summary>

```python
with open("nombres.txt", "w", encoding="utf-8") as f:
    for i in range(1, 11):
        f.write(f"{i}\n")
```
</details>

**Ex 12.2** — Relis `nombres.txt` et calcule la somme → `55`.
<details><summary>Correction</summary>

```python
with open("nombres.txt", "w", encoding="utf-8") as f:   # (recrée le fichier pour être autonome)
    for i in range(1, 11):
        f.write(f"{i}\n")

total = 0
with open("nombres.txt", "r", encoding="utf-8") as f:
    for ligne in f:
        total += int(ligne.strip())   # le texte "7\n" → 7
assert total == 55
```
</details>

**Ex 12.3** — Écris `"le modèle lit\nle texte\n"` dans `texte.txt`, puis compte les **mots** du fichier → `5`.
<details><summary>Correction</summary>

```python
with open("texte.txt", "w", encoding="utf-8") as f:
    f.write("le modèle lit\nle texte\n")

nb_mots = 0
with open("texte.txt", "r", encoding="utf-8") as f:
    for ligne in f:
        nb_mots += len(ligne.split())
assert nb_mots == 5
```
</details>

**Ex 12.4** — `noter_seance(date)` **ajoute** `"<date> : séance faite"` à `suivi.txt` à chaque appel. Appelle-la 2 fois et vérifie qu'il y a 2 lignes.
<details><summary>Correction</summary>

```python
def noter_seance(date):
    with open("suivi.txt", "a", encoding="utf-8") as f:   # "a" = append
        f.write(f"{date} : séance faite\n")

open("suivi.txt", "w").close()        # repartir d'un fichier vide pour le test
noter_seance("2026-11-13")
noter_seance("2026-11-16")
with open("suivi.txt", encoding="utf-8") as f:
    assert len(f.readlines()) == 2
```
Bonus : garde cette fonction, elle peut devenir ton vrai suivi de séances.
</details>

**Ex 12.5** — Écris ce CSV dans `notes.csv`, puis calcule la moyenne des notes (en sautant l'en-tête) → `13.5`.
```
nom,note
Alice,12
Bob,15
```
<details><summary>Correction</summary>

```python
with open("notes.csv", "w", encoding="utf-8") as f:
    f.write("nom,note\nAlice,12\nBob,15\n")

notes = []
with open("notes.csv", encoding="utf-8") as f:
    next(f)                               # saute la 1re ligne (en-tête)
    for ligne in f:
        nom, note = ligne.strip().split(",")   # unpacking (notion 10)
        notes.append(float(note))
assert sum(notes) / len(notes) == 13.5
```
</details>

---

# Notion 13 — Exceptions

## 📖 Cours
Une **exception** = une erreur qui arrête le programme… sauf si on la **rattrape**.
```python
try:
    x = int("abc")            # code qui PEUT échouer
except ValueError:
    x = None                  # ce qu'on fait si ça échoue
```
| Exception | Quand |
|---|---|
| `ValueError` | bonne type, mauvaise valeur (`int("abc")`) |
| `ZeroDivisionError` | division par 0 |
| `FileNotFoundError` | fichier absent |
| `KeyError` | clé absente d'un dict |
| `TypeError` | mauvais type (`"a" + 1`) |

**Lever** soi-même une erreur (refuser une donnée invalide) : `raise ValueError("message")`.

**🧭 Chemin de pensée :** 1. **Qu'est-ce qui peut échouer ?** 2. **Quelle exception** exactement ? 3. **Que faire** : valeur par défaut, message, ou laisser remonter ?

## 🧪 Exemple guidé
```python
def division_sure(a, b):
    try:
        return a / b
    except ZeroDivisionError:
        return None

assert division_sure(10, 2) == 5
assert division_sure(1, 0) is None
```
On rattrape **une exception précise**, jamais un `except:` nu (il cacherait tous les bugs).

## ✏️ Exercices

**Ex 13.1** — `vers_entier(s)` renvoie l'entier ou `None`. Tests : `vers_entier("42") == 42`, `vers_entier("4x") is None`.
<details><summary>Correction</summary>

```python
def vers_entier(s):
    try:
        return int(s)
    except ValueError:
        return None

assert vers_entier("42") == 42
assert vers_entier("4x") is None
```
</details>

**Ex 13.2** — `lire_fichier(chemin)` renvoie le contenu, ou `""` si le fichier n'existe pas. Test : `lire_fichier("existe_pas.txt") == ""`.
<details><summary>Correction</summary>

```python
def lire_fichier(chemin):
    try:
        with open(chemin, encoding="utf-8") as f:
            return f.read()
    except FileNotFoundError:
        return ""

assert lire_fichier("existe_pas.txt") == ""
```
</details>

**Ex 13.3** — `somme_valides(lst)` additionne les éléments convertibles en entier et **ignore** les autres. Test : `somme_valides(["3", "x", "4"]) == 7`.
<details><summary>Correction</summary>

```python
def somme_valides(lst):
    total = 0
    for s in lst:
        try:
            total += int(s)
        except ValueError:
            pass             # on ignore
    return total

assert somme_valides(["3", "x", "4"]) == 7
```
</details>

**Ex 13.4** — `retirer(solde, montant)` lève `ValueError` si `montant > solde`, sinon renvoie le nouveau solde. Tests : `retirer(100, 30) == 70` ; `retirer(10, 30)` doit lever l'erreur.
<details><summary>Correction</summary>

```python
def retirer(solde, montant):
    if montant > solde:
        raise ValueError("Solde insuffisant")
    return solde - montant

assert retirer(100, 30) == 70
try:
    retirer(10, 30)
    assert False, "aurait dû lever une erreur"
except ValueError:
    pass
```
Ici on **lève** l'erreur ; c'est l'**appelant** qui décide quoi en faire.
</details>

**Ex 13.5** — `age_valide(age)` lève `ValueError` si l'âge n'est pas entre 0 et 130, sinon le renvoie. Tests : `age_valide(23) == 23` ; `age_valide(-4)` lève l'erreur.
<details><summary>Correction</summary>

```python
def age_valide(age):
    if not 0 <= age <= 130:
        raise ValueError(f"Âge invalide : {age}")
    return age

assert age_valide(23) == 23
try:
    age_valide(-4)
    assert False
except ValueError:
    pass
```
Même moule que 13.4. (Au passage : c'est exactement une **règle métier** du cours de modélisation, traduite en code.)
</details>

---

# Notion 14 — Récursivité

## 📖 Cours
Une fonction **récursive** s'appelle elle-même sur un problème **plus petit**.
Deux ingrédients **obligatoires** :
1. **Cas de base** : le cas si petit qu'on connaît la réponse directement (sinon : boucle infinie).
2. **Appel récursif** : sur une version **plus petite** du problème.

**🧭 Chemin de pensée (le « saut de confiance ») :**
1. Quel est le **plus petit cas** ? → `return` direct.
2. **Suppose** que la fonction marche déjà pour `n-1` (ou pour la liste sans son 1ᵉʳ élément).
3. Comment passer de la réponse pour `n-1` à la réponse pour `n` ?

Ne « déroule » pas tous les appels dans ta tête : **fais confiance** à l'étape 2.

## 🧪 Exemple guidé
**Problème :** factorielle, `n! = n × (n-1)!`, et `0! = 1`.
```python
def factorielle(n):
    if n == 0:                        # 1. cas de base
        return 1
    return n * factorielle(n - 1)     # 3. si je connais (n-1)!, je multiplie par n

assert factorielle(0) == 1
assert factorielle(6) == 720
```
`factorielle(3)` = 3 × `factorielle(2)` = 3 × 2 × `factorielle(1)` = 3 × 2 × 1 × `factorielle(0)` = 3 × 2 × 1 × 1.

## ✏️ Exercices

**Ex 14.1** — `somme(n)` = 1 + … + n, récursive. Test : `somme(100) == 5050`.
<details><summary>Correction</summary>

```python
def somme(n):
    if n == 0:
        return 0
    return n + somme(n - 1)

assert somme(100) == 5050
```
Exactement l'exemple, avec `+` et un cas de base à 0.
</details>

**Ex 14.2** — `puissance(b, e)` récursive (`b^e = b × b^(e-1)`, `b^0 = 1`). Test : `puissance(2, 10) == 1024`.
<details><summary>Correction</summary>

```python
def puissance(b, e):
    if e == 0:
        return 1
    return b * puissance(b, e - 1)

assert puissance(2, 10) == 1024
```
</details>

**Ex 14.3** — `longueur(lst)` récursive, sans `len`. Test : `longueur([4, 8, 1]) == 3`.
<details><summary>Correction</summary>

```python
def longueur(lst):
    if lst == []:
        return 0
    return 1 + longueur(lst[1:])     # 1 (le premier) + la longueur du reste

assert longueur([4, 8, 1]) == 3
```
Le « plus petit problème » ici : la liste **sans son premier élément** (`lst[1:]`).
</details>

**Ex 14.4** — `inverse(s)` récursive. Test : `inverse("Java") == "avaJ"`.
<details><summary>Correction</summary>

```python
def inverse(s):
    if len(s) <= 1:
        return s
    return s[-1] + inverse(s[:-1])   # dernier caractère + l'inverse du reste

assert inverse("Java") == "avaJ"
```
</details>

**Ex 14.5** — `somme_chiffres(n)` récursive (reprends l'astuce `% 10` / `// 10` de la notion 4). Test : `somme_chiffres(4827) == 21`.
<details><summary>Correction</summary>

```python
def somme_chiffres(n):
    if n < 10:
        return n
    return n % 10 + somme_chiffres(n // 10)

assert somme_chiffres(4827) == 21
```
Même problème que l'Ex 4.2, autre outil : tu vois qu'une boucle `while` et une récursion peuvent faire la même chose.
</details>

---

# Notion 15 — Classes & objets

## 📖 Cours
Une **classe** = un **moule** ; un **objet** = une chose fabriquée avec ce moule. (Exactement ce que tu vois en **Java** et en **UML** ce semestre.)
```python
class Compte:
    def __init__(self, titulaire, solde=0):   # le CONSTRUCTEUR
        self.titulaire = titulaire            # ATTRIBUTS : self.xxx
        self.solde = solde

    def deposer(self, montant):               # MÉTHODE : 1er paramètre = self
        self.solde += montant

c = Compte("Léa")      # création d'un objet (Python appelle __init__)
c.deposer(50)
c.solde                # 50
```
`self` = « **cet objet-ci** ». En Java, c'est `this`.

**🧭 Chemin de pensée — la même analyse grammaticale qu'en modélisation :**
- le **nom** principal → la **classe**
- ses **valeurs** (nom, solde, âge) → les **attributs** dans `__init__`
- ses **verbes** (déposer, retirer) → les **méthodes**

## 🧪 Exemple guidé
**Problème :** un compte bancaire qu'on peut créditer et débiter (sans passer sous 0).
```python
class Compte:
    def __init__(self, titulaire, solde=0):
        self.titulaire = titulaire
        self.solde = solde

    def deposer(self, montant):
        self.solde += montant

    def retirer(self, montant):
        if montant > self.solde:
            raise ValueError("Solde insuffisant")     # notion 13
        self.solde -= montant

c = Compte("Léa", 100)
c.deposer(50)
c.retirer(30)
assert c.solde == 120
```
Tu reconnais l'Ex 13.4 : la règle métier vit maintenant **dans** l'objet.

## ✏️ Exercices

**Ex 15.1** — Classe `Rectangle(longueur, largeur)` avec `aire()` et `perimetre()`. Test : `r = Rectangle(7, 3)` → `r.aire() == 21`, `r.perimetre() == 20`.
<details><summary>Correction</summary>

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur

    def aire(self):
        return self.longueur * self.largeur

    def perimetre(self):
        return 2 * (self.longueur + self.largeur)

r = Rectangle(7, 3)
assert r.aire() == 21 and r.perimetre() == 20
```
L'Ex 1.1, transformé en objet.
</details>

**Ex 15.2** — Classe `Compteur` : attribut `valeur` à 0, méthodes `incrementer()` et `reset()`.
<details><summary>Correction</summary>

```python
class Compteur:
    def __init__(self):
        self.valeur = 0

    def incrementer(self):
        self.valeur += 1

    def reset(self):
        self.valeur = 0

c = Compteur()
c.incrementer(); c.incrementer()
assert c.valeur == 2
c.reset()
assert c.valeur == 0
```
</details>

**Ex 15.3** — Classe `Etudiant(nom)` : une liste `notes` vide au départ, `ajouter_note(n)`, `moyenne()` (0 si aucune note).
<details><summary>Correction</summary>

```python
class Etudiant:
    def __init__(self, nom):
        self.nom = nom
        self.notes = []

    def ajouter_note(self, n):
        self.notes.append(n)

    def moyenne(self):
        if not self.notes:
            return 0
        return sum(self.notes) / len(self.notes)

e = Etudiant("Vladimir")
assert e.moyenne() == 0
e.ajouter_note(12); e.ajouter_note(16)
assert e.moyenne() == 14
```
Ex 7.3 dans un objet.
</details>

**Ex 15.4** — Classe `Panier` : dict `articles` (nom → prix), `ajouter(nom, prix)`, `total()`.
<details><summary>Correction</summary>

```python
class Panier:
    def __init__(self):
        self.articles = {}

    def ajouter(self, nom, prix):
        self.articles[nom] = prix

    def total(self):
        return sum(self.articles.values())

p = Panier()
p.ajouter("clavier", 40)
p.ajouter("souris", 15)
assert p.total() == 55
```
</details>

**Ex 15.5** — Classe `Velo(identifiant, batterie=100)` : `rouler(km)` retire 2 % par km **sans descendre sous 0**, `est_vide()`.
<details><summary>Correction</summary>

```python
class Velo:
    def __init__(self, identifiant, batterie=100):
        self.identifiant = identifiant
        self.batterie = batterie

    def rouler(self, km):
        self.batterie = max(0, self.batterie - 2 * km)

    def est_vide(self):
        return self.batterie == 0

v = Velo("v7")
v.rouler(10)
assert v.batterie == 80
v.rouler(100)
assert v.batterie == 0 and v.est_vide()
```
`max(0, …)` : une façon courte d'empêcher de passer sous 0.
</details>

---

# Notion 16 — Méthodes spéciales (`__str__`, `__len__`, `__getitem__`…)

## 📖 Cours
Les méthodes entourées de `__` sont appelées **automatiquement** par Python :

| Tu écris… | Python appelle… |
|---|---|
| `print(obj)` / `str(obj)` | `obj.__str__()` |
| `len(obj)` | `obj.__len__()` |
| `obj[i]` | `obj.__getitem__(i)` |
| `a + b` | `a.__add__(b)` |
| `a == b` | `a.__eq__(b)` |

⭐ **Pourquoi c'est important pour toi :** dans PyTorch (le livre LLM), un jeu de données est une classe `Dataset` avec **exactement** `__len__` et `__getitem__`. L'Ex 16.4 est ce pattern.

**🧭 Chemin de pensée :** « je voudrais pouvoir écrire `len(x)` / `x[i]` / `print(x)` sur mon objet » → j'implémente la méthode spéciale correspondante.

## 🧪 Exemple guidé
```python
class Playlist:
    def __init__(self, nom):
        self.nom = nom
        self.morceaux = []

    def ajouter(self, titre):
        self.morceaux.append(titre)

    def __len__(self):
        return len(self.morceaux)

    def __getitem__(self, i):
        return self.morceaux[i]

    def __str__(self):
        return f"{self.nom} ({len(self)} morceaux)"

p = Playlist("Matin")
p.ajouter("A"); p.ajouter("B")
assert len(p) == 2
assert p[1] == "B"
assert str(p) == "Matin (2 morceaux)"
```
L'objet **délègue** simplement à sa liste interne.

## ✏️ Exercices

**Ex 16.1** — Ajoute `__str__` à `Rectangle` pour que `str(Rectangle(7, 3)) == "Rectangle 7x3"`.
<details><summary>Correction</summary>

```python
class Rectangle:
    def __init__(self, longueur, largeur):
        self.longueur = longueur
        self.largeur = largeur

    def __str__(self):
        return f"Rectangle {self.longueur}x{self.largeur}"

assert str(Rectangle(7, 3)) == "Rectangle 7x3"
```
</details>

**Ex 16.2** — Classe `Phrase(texte)` où `len()` renvoie le **nombre de mots**. Test : `len(Phrase("je code le matin")) == 4`.
<details><summary>Correction</summary>

```python
class Phrase:
    def __init__(self, texte):
        self.texte = texte

    def __len__(self):
        return len(self.texte.split())

assert len(Phrase("je code le matin")) == 4
```
</details>

**Ex 16.3** — Classe `Vecteur(x, y)` avec `__add__` (renvoie un **nouveau** Vecteur) et `__str__` → `"(4, 6)"`.
<details><summary>Correction</summary>

```python
class Vecteur:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, autre):
        return Vecteur(self.x + autre.x, self.y + autre.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

assert str(Vecteur(1, 2) + Vecteur(3, 4)) == "(4, 6)"
```
</details>

**Ex 16.4** — ⭐ Classe `Dataset(donnees)` avec `__len__` et `__getitem__`. Test : `ds = Dataset([("bonjour", 1), ("salut", 1), ("adieu", 0)])` → `len(ds) == 3`, `ds[2] == ("adieu", 0)`.
<details><summary>Correction</summary>

```python
class Dataset:
    def __init__(self, donnees):
        self.donnees = donnees

    def __len__(self):
        return len(self.donnees)

    def __getitem__(self, i):
        return self.donnees[i]

ds = Dataset([("bonjour", 1), ("salut", 1), ("adieu", 0)])
assert len(ds) == 3
assert ds[2] == ("adieu", 0)
texte, etiquette = ds[0]        # unpacking (notion 10)
assert etiquette == 1
```
C'est **mot pour mot** la structure d'un `torch.utils.data.Dataset`.
</details>

**Ex 16.5** — Classe `Temperature(celsius)` avec `__eq__` : deux températures sont égales si leurs degrés le sont. Test : `Temperature(20) == Temperature(20)` et `Temperature(20) != Temperature(25)`.
<details><summary>Correction</summary>

```python
class Temperature:
    def __init__(self, celsius):
        self.celsius = celsius

    def __eq__(self, autre):
        return self.celsius == autre.celsius

assert Temperature(20) == Temperature(20)
assert Temperature(20) != Temperature(25)
```
Sans `__eq__`, `==` compare l'**identité** (le même objet en mémoire) → `False`.
</details>

---

# Notion 17 — Héritage

## 📖 Cours
```python
class Animal:                          # classe PARENT
    def __init__(self, nom):
        self.nom = nom
    def parler(self):
        return "..."

class Chien(Animal):                   # Chien EST UN Animal
    def parler(self):                  # REDÉFINITION
        return "Wouf"

class Chat(Animal):
    def __init__(self, nom, interieur):
        super().__init__(nom)          # on réutilise le constructeur du parent
        self.interieur = interieur     # + un attribut EN PLUS
```
**Le test de modélisation s'applique tel quel** : *est-un ? toujours ? différence réelle ?* → 3 × oui → héritage.
Parent « abstrait » (qu'on n'instancie pas) : sa méthode fait `raise NotImplementedError`.

**Polymorphisme :** une liste de formes différentes, **le même appel**, chacune répond **à sa façon** :
```python
for a in [Chien("Rex"), Chat("Mia", True)]:
    print(a.parler())
```

**🧭 Chemin de pensée :** 1. Qu'est-ce qui est **commun** ? → parent. 2. Qu'est-ce qui **diffère** ? → redéfinition ou attribut en plus. 3. Le parent a un constructeur ? → `super().__init__(...)`.

## 🧪 Exemple guidé
**Problème (celui de ton mini-cours UML !) :** un véhicule est soit une voiture, soit une moto ; chacun calcule sa taxe différemment.
```python
class Vehicule:
    def __init__(self, immat):
        self.immat = immat
    def taxe(self):
        raise NotImplementedError    # Vehicule est abstrait

class Voiture(Vehicule):
    def taxe(self):
        return 200

class Moto(Vehicule):
    def taxe(self):
        return 80

parc = [Voiture("AA-123"), Moto("BB-456"), Voiture("CC-789")]
assert sum(v.taxe() for v in parc) == 480
```
Le diagramme UML devient du code **ligne pour ligne** : c'est pour ça que les deux cours se renforcent.

## ✏️ Exercices

**Ex 17.1** — `Animal(nom)` avec `parler()`, puis `Chien` → `"Wouf"`, `Chat` → `"Miaou"`. Test : `[a.parler() for a in [Chien("Rex"), Chat("Mia")]] == ["Wouf", "Miaou"]`.
<details><summary>Correction</summary>

```python
class Animal:
    def __init__(self, nom):
        self.nom = nom
    def parler(self):
        raise NotImplementedError

class Chien(Animal):
    def parler(self):
        return "Wouf"

class Chat(Animal):
    def parler(self):
        return "Miaou"

assert [a.parler() for a in [Chien("Rex"), Chat("Mia")]] == ["Wouf", "Miaou"]
```
</details>

**Ex 17.2** — `Forme` avec `aire()`, puis `Carre(cote)` et `Cercle(r)` (π ≈ 3.14159). Test : aire totale de `[Carre(2), Cercle(1)]` arrondie à 2 décimales → `7.14`.
<details><summary>Correction</summary>

```python
class Forme:
    def aire(self):
        raise NotImplementedError

class Carre(Forme):
    def __init__(self, cote):
        self.cote = cote
    def aire(self):
        return self.cote ** 2

class Cercle(Forme):
    def __init__(self, r):
        self.r = r
    def aire(self):
        return 3.14159 * self.r ** 2

formes = [Carre(2), Cercle(1)]
assert round(sum(f.aire() for f in formes), 2) == 7.14
```
</details>

**Ex 17.3** — `Employe(nom, salaire)` avec `salaire_total()`. `Manager(nom, salaire, prime)` : utilise `super().__init__` et redéfinit `salaire_total()` = salaire + prime.
<details><summary>Correction</summary>

```python
class Employe:
    def __init__(self, nom, salaire):
        self.nom = nom
        self.salaire = salaire
    def salaire_total(self):
        return self.salaire

class Manager(Employe):
    def __init__(self, nom, salaire, prime):
        super().__init__(nom, salaire)
        self.prime = prime
    def salaire_total(self):
        return super().salaire_total() + self.prime

assert Employe("A", 2000).salaire_total() == 2000
assert Manager("B", 3000, 500).salaire_total() == 3500
```
`super().salaire_total()` : on **réutilise** le calcul du parent au lieu de le recopier.
</details>

**Ex 17.4** — `Velo(identifiant)` avec `__str__` → `"Vélo v3"`. `VeloElectrique(identifiant, batterie)` ajoute la batterie et redéfinit `__str__` → `"Vélo v7 (45%)"`.
<details><summary>Correction</summary>

```python
class Velo:
    def __init__(self, identifiant):
        self.identifiant = identifiant
    def __str__(self):
        return f"Vélo {self.identifiant}"

class VeloElectrique(Velo):
    def __init__(self, identifiant, batterie):
        super().__init__(identifiant)
        self.batterie = batterie
    def __str__(self):
        return f"{super().__str__()} ({self.batterie}%)"

assert str(Velo("v3")) == "Vélo v3"
assert str(VeloElectrique("v7", 45)) == "Vélo v7 (45%)"
```
C'est l'exercice B2b de ton mini-cours UML, codé.
</details>

**Ex 17.5** — `Compte(titulaire, solde)` avec `deposer`. `CompteEpargne(titulaire, solde, taux)` ajoute `appliquer_interets()`. Test : `CompteEpargne("Léa", 1000, 0.03)` puis `deposer(100)` puis intérêts → solde `1133.0`.
<details><summary>Correction</summary>

```python
class Compte:
    def __init__(self, titulaire, solde=0):
        self.titulaire = titulaire
        self.solde = solde
    def deposer(self, montant):
        self.solde += montant

class CompteEpargne(Compte):
    def __init__(self, titulaire, solde, taux):
        super().__init__(titulaire, solde)
        self.taux = taux
    def appliquer_interets(self):
        self.solde = round(self.solde * (1 + self.taux), 2)

c = CompteEpargne("Léa", 1000, 0.03)
c.deposer(100)              # hérité, pas réécrit
c.appliquer_interets()
assert c.solde == 1133.0
```
</details>

---

# Notion 18 — `lambda`, `sorted`, `max(key=...)`

## 📖 Cours
Une **lambda** = une mini-fonction anonyme d'**une expression** : `lambda x: x * 2`.
Son usage principal : dire **selon quoi** trier ou chercher un max.
```python
sorted(liste, key=lambda x: ..., reverse=True)   # trie selon la valeur calculée
max(liste, key=lambda x: ...)                   # l'élément qui a la plus grande valeur calculée
max(d, key=d.get)                               # la clé du dict qui a la plus grande valeur
```
Trier selon **2 critères** : la clé renvoie un **tuple** `(critère1, critère2)`. Pour inverser un critère numérique : `-x`.

**🧭 Chemin de pensée :** pour **un** élément, **quelle valeur** veux-je comparer ? → c'est le corps de la lambda.

## 🧪 Exemple guidé
**Problème :** trier des élèves par note décroissante.
```python
eleves = [("Alice", 12), ("Bob", 15), ("Chloé", 9)]
classement = sorted(eleves, key=lambda e: e[1], reverse=True)
assert classement == [("Bob", 15), ("Alice", 12), ("Chloé", 9)]
```
Pour un élément `e = ("Alice", 12)`, on compare `e[1]` = la note.

## ✏️ Exercices

**Ex 18.1** — Trie `["python", "c", "java", "go"]` par longueur croissante. Test : `["c", "go", "java", "python"]`.
<details><summary>Correction</summary>

```python
mots = ["python", "c", "java", "go"]
assert sorted(mots, key=lambda m: len(m)) == ["c", "go", "java", "python"]
# équivalent : key=len
```
</details>

**Ex 18.2** — Le mot le plus long de `"le transformeur prédit le mot suivant"`. Test : `"transformeur"`.
<details><summary>Correction</summary>

```python
phrase = "le transformeur prédit le mot suivant"
assert max(phrase.split(), key=len) == "transformeur"
```
</details>

**Ex 18.3** — Top 2 des mots les plus fréquents (reprends le compteur de la notion 9) dans `"a b a c b a"`. Test : `[("a", 3), ("b", 2)]`.
<details><summary>Correction</summary>

```python
compte = {}
for m in "a b a c b a".split():
    compte[m] = compte.get(m, 0) + 1

top2 = sorted(compte.items(), key=lambda kv: kv[1], reverse=True)[:2]
assert top2 == [("a", 3), ("b", 2)]
```
`.items()` donne des tuples `(mot, nb)` → on trie sur `kv[1]`, puis on **tranche** `[:2]` (notion 6).
</details>

**Ex 18.4** — Trie des produits par prix : `[{"nom": "clé USB", "prix": 12}, {"nom": "écran", "prix": 150}, {"nom": "câble", "prix": 5}]`. Test : les noms dans l'ordre sont `["câble", "clé USB", "écran"]`.
<details><summary>Correction</summary>

```python
produits = [{"nom": "clé USB", "prix": 12}, {"nom": "écran", "prix": 150}, {"nom": "câble", "prix": 5}]
tries = sorted(produits, key=lambda p: p["prix"])
assert [p["nom"] for p in tries] == ["câble", "clé USB", "écran"]
```
</details>

**Ex 18.5** — Trie par note **décroissante**, puis par nom **alphabétique** en cas d'égalité : `[("Tom", 12), ("Léa", 15), ("Ana", 12)]` → `[("Léa", 15), ("Ana", 12), ("Tom", 12)]`.
<details><summary>Correction</summary>

```python
eleves = [("Tom", 12), ("Léa", 15), ("Ana", 12)]
res = sorted(eleves, key=lambda e: (-e[1], e[0]))
assert res == [("Léa", 15), ("Ana", 12), ("Tom", 12)]
```
Le `-` inverse l'ordre de la note seulement ; le nom reste croissant.
</details>

---

# Notion 19 — NumPy : tableaux & formes

## 📖 Cours
Installe une fois : `pip install numpy`. Puis `import numpy as np`.
Un **tableau NumPy** = une grille de nombres de **même type**, ultra-rapide. Les LLM ne manipulent **que** ça (en PyTorch, ça s'appelle un *tensor*, même logique).

```python
a = np.array([[1, 2, 3],
              [4, 5, 6]])
a.shape        # (2, 3)  → 2 lignes, 3 colonnes   ⭐ LA propriété à toujours vérifier
a.ndim         # 2 dimensions
np.zeros((2, 3)), np.ones((3,)), np.arange(6)      # [0 1 2 3 4 5]
np.arange(6).reshape(2, 3)                         # même données, nouvelle forme
a[1, 2]        # 6  → ligne 1, colonne 2
a[0, :]        # ligne 0 entière → [1 2 3]
a[:, 1]        # colonne 1 entière → [2 5]
```
`reshape` ne marche que si le **nombre total d'éléments** est conservé (2 × 3 = 6).

**🧭 Chemin de pensée :** avant tout calcul, **écris la forme** (shape) sur papier. `[lignes, colonnes]` : `:` veut dire « tout ».

## 🧪 Exemple guidé
```python
import numpy as np

m = np.arange(12).reshape(3, 4)
# [[ 0  1  2  3]
#  [ 4  5  6  7]
#  [ 8  9 10 11]]
assert m.shape == (3, 4)
assert m[1, 2] == 6                    # ligne 1, colonne 2
assert list(m[:, 0]) == [0, 4, 8]      # 1re colonne
assert list(m[2, :]) == [8, 9, 10, 11] # dernière ligne
```

## ✏️ Exercices

**Ex 19.1** — Crée un tableau de zéros de forme (2, 5). Test : `z.shape == (2, 5)` et `z.sum() == 0`.
<details><summary>Correction</summary>

```python
import numpy as np
z = np.zeros((2, 5))
assert z.shape == (2, 5) and z.sum() == 0
```
</details>

**Ex 19.2** — `m = np.arange(1, 10).reshape(3, 3)`. Récupère la diagonale `[1, 5, 9]` avec une compréhension.
<details><summary>Correction</summary>

```python
import numpy as np
m = np.arange(1, 10).reshape(3, 3)
diag = [m[i, i] for i in range(3)]
assert diag == [1, 5, 9]
# (NumPy a aussi np.diag(m))
```
</details>

**Ex 19.3** — `m = np.arange(12).reshape(4, 3)`. Récupère la **dernière colonne**. Test : `[2, 5, 8, 11]`.
<details><summary>Correction</summary>

```python
import numpy as np
m = np.arange(12).reshape(4, 3)
assert list(m[:, -1]) == [2, 5, 8, 11]
```
L'index négatif `-1` de la notion 6 marche aussi ici.
</details>

**Ex 19.4** — Mets `np.arange(24)` en forme (2, 3, 4). Vérifie la forme et que `t[1, 2, 3] == 23`.
<details><summary>Correction</summary>

```python
import numpy as np
t = np.arange(24).reshape(2, 3, 4)
assert t.shape == (2, 3, 4)
assert t[1, 2, 3] == 23
```
⭐ 3 dimensions = la forme typique d'un lot de phrases dans un LLM : `(batch, nb_tokens, dimension)`.
</details>

**Ex 19.5** — Dans `np.arange(16).reshape(4, 4)`, extrais le bloc 2×2 en haut à gauche. Test : `[[0, 1], [4, 5]]`.
<details><summary>Correction</summary>

```python
import numpy as np
m = np.arange(16).reshape(4, 4)
bloc = m[:2, :2]
assert bloc.tolist() == [[0, 1], [4, 5]]
```
Slicing sur **chaque** dimension : `[lignes 0-1, colonnes 0-1]`.
</details>

---

# Notion 20 — NumPy : calculs, broadcasting, produit matriciel

## 📖 Cours
**Opérations élément par élément** (plus besoin de boucle !) : `a + b`, `a * 2`, `a ** 2`, `np.exp(a)`.
**Agrégations avec `axis`** :
```
            axis=1 →  (on écrase les colonnes : un résultat PAR LIGNE)
         ┌──────────┐
axis=0   │ 1  2  3  │
  ↓      │ 4  5  6  │
         └──────────┘
a.sum(axis=0) → [5 7 9]      (un résultat par colonne)
a.sum(axis=1) → [ 6 15]      (un résultat par ligne)
```
**Broadcasting** : une matrice (2, 3) + un vecteur (3,) → le vecteur est **ajouté à chaque ligne**.
**Produit matriciel** : `A @ B`. Règle des formes : `(n, k) @ (k, m) → (n, m)` — les dimensions **intérieures** doivent être égales.

**🧭 Chemin de pensée :** écris les **formes** avant de calculer : `(2,3) @ (3,2)` → le 3 « s'annule » → résultat `(2,2)`.

## 🧪 Exemple guidé
**Problème :** 3 étudiants × 2 matières. Moyenne **par étudiant**.
```python
import numpy as np
notes = np.array([[12, 16],
                  [ 9, 11],
                  [15, 15]])
moy = notes.mean(axis=1)          # un résultat par LIGNE (= par étudiant)
assert moy.tolist() == [14.0, 10.0, 15.0]
```
« Par étudiant » = par ligne = on écrase les colonnes = `axis=1`.

## ✏️ Exercices

**Ex 20.1** — Produit scalaire de `[1, 2, 3]` et `[4, 5, 6]` avec `@`. Test : `32` (compare avec l'Ex 10.3 !).
<details><summary>Correction</summary>

```python
import numpy as np
u = np.array([1, 2, 3])
v = np.array([4, 5, 6])
assert u @ v == 32
```
La boucle `zip` de la notion 10 en un seul symbole.
</details>

**Ex 20.2** — Avec la matrice `notes` de l'exemple, moyenne **par matière**. Test : `[12.0, 14.0]`.
<details><summary>Correction</summary>

```python
import numpy as np
notes = np.array([[12, 16], [9, 11], [15, 15]])
assert notes.mean(axis=0).tolist() == [12.0, 14.0]
```
Par matière = par colonne = `axis=0`.
</details>

**Ex 20.3** — Ajoute le bonus `[1, 0, 2]` à **chaque ligne** de `[[10, 10, 10], [12, 8, 14]]`. Test : `[[11, 10, 12], [13, 8, 16]]`.
<details><summary>Correction</summary>

```python
import numpy as np
m = np.array([[10, 10, 10], [12, 8, 14]])
bonus = np.array([1, 0, 2])
assert (m + bonus).tolist() == [[11, 10, 12], [13, 8, 16]]
```
Broadcasting : (2, 3) + (3,) → le bonus est « recopié » sur chaque ligne.
</details>

**Ex 20.4** — `A = [[1, 2, 3], [4, 5, 6]]`, `B = [[1, 0], [0, 1], [1, 1]]`. Prédis la forme **avant** de calculer, puis vérifie : `A @ B == [[4, 5], [10, 11]]`.
<details><summary>Correction</summary>

```python
import numpy as np
A = np.array([[1, 2, 3], [4, 5, 6]])    # (2, 3)
B = np.array([[1, 0], [0, 1], [1, 1]])  # (3, 2)
C = A @ B                               # (2, 3) @ (3, 2) → (2, 2)
assert C.shape == (2, 2)
assert C.tolist() == [[4, 5], [10, 11]]
```
Case (0,0) = ligne 0 de A · colonne 0 de B = 1×1 + 2×0 + 3×1 = 4 : chaque case est un **produit scalaire**.
</details>

**Ex 20.5** — ⭐ **Softmax** : `softmax(x) = exp(x) / somme(exp(x))`. Calcule-la pour `[1, 2, 3]`. Test : arrondie à 3 décimales → `[0.09, 0.245, 0.665]`, et la somme vaut 1.
<details><summary>Correction</summary>

```python
import numpy as np
def softmax(x):
    e = np.exp(x)
    return e / e.sum()

s = softmax(np.array([1.0, 2.0, 3.0]))
assert np.round(s, 3).tolist() == [0.09, 0.245, 0.665]
assert abs(s.sum() - 1) < 1e-9
```
⭐ C'est **la** fonction qui transforme les scores d'un LLM en **probabilités** du mot suivant. Tu viens d'écrire une pièce de GPT.
</details>

---

# Notion 21 — 🏁 Mini-tokenizer (chapitre 2 du livre)

## 📖 Cours
Un LLM ne lit pas du texte, il lit des **nombres**. Le **tokenizer** fait la traduction :
```
"le chat dort"  ──tokeniser──►  ["le", "chat", "dort"]  ──encoder──►  [3, 0, 1]
[3, 0, 1]       ──décoder───►  "le chat dort"
```
Les 4 briques — **tu les as toutes déjà codées** :

| Brique | Ce qu'elle fait | Déjà vu en |
|---|---|---|
| tokeniser | texte → liste de mots | `split` (notion 6) |
| vocabulaire | mots uniques triés → dict `mot → id` | `set` + `sorted` (11.5), `enumerate` (10) |
| encoder | mots → ids, `<unk>` si mot inconnu | `dict.get` (9.3) |
| décoder | ids → mots | inverser un dict (9.5) |

**🧭 Chemin de pensée :** une brique = une fonction ; puis on les **range dans une classe** (notion 15) avec `__len__` (notion 16).

## 🧪 Exemple guidé
```python
texte = "le chat dort le chien dort"
mots = texte.split()
vocab = {mot: i for i, mot in enumerate(sorted(set(mots)))}
# {'chat': 0, 'chien': 1, 'dort': 2, 'le': 3}
ids = [vocab[m] for m in "le chat dort".split()]
assert ids == [3, 0, 2]
```
Nouveau : `{cle: valeur for ...}` = compréhension de **dictionnaire** (même logique que la notion 8).

## ✏️ Exercices

**Ex 21.1** — `tokeniser(texte)` : minuscules, et la ponctuation `.` et `,` devient un token à part. Test : `tokeniser("Le chat dort, le chien aussi.") == ["le", "chat", "dort", ",", "le", "chien", "aussi", "."]`. *(indice : `replace(",", " , ")`)*
<details><summary>Correction</summary>

```python
def tokeniser(texte):
    texte = texte.lower().replace(",", " , ").replace(".", " . ")
    return texte.split()

assert tokeniser("Le chat dort, le chien aussi.") == ["le", "chat", "dort", ",", "le", "chien", "aussi", "."]
```
</details>

**Ex 21.2** — `construire_vocab(tokens)` : dict `mot → id` trié, avec `"<unk>"` ajouté **à la fin**. Test : `construire_vocab(["b", "a", "b"]) == {"a": 0, "b": 1, "<unk>": 2}`.
<details><summary>Correction</summary>

```python
def construire_vocab(tokens):
    vocab = {mot: i for i, mot in enumerate(sorted(set(tokens)))}
    vocab["<unk>"] = len(vocab)
    return vocab

assert construire_vocab(["b", "a", "b"]) == {"a": 0, "b": 1, "<unk>": 2}
```
</details>

**Ex 21.3** — `encoder(tokens, vocab)` : un mot inconnu devient l'id de `"<unk>"`. Test avec `vocab = {"a": 0, "b": 1, "<unk>": 2}` : `encoder(["a", "z", "b"], vocab) == [0, 2, 1]`.
<details><summary>Correction</summary>

```python
def encoder(tokens, vocab):
    return [vocab.get(t, vocab["<unk>"]) for t in tokens]

vocab = {"a": 0, "b": 1, "<unk>": 2}
assert encoder(["a", "z", "b"], vocab) == [0, 2, 1]
```
</details>

**Ex 21.4** — `decoder(ids, vocab)` renvoie la phrase (mots séparés par des espaces). Test : `decoder([1, 0], {"a": 0, "b": 1, "<unk>": 2}) == "b a"`. *(indice : inverser le dict, puis `" ".join(...)`)*
<details><summary>Correction</summary>

```python
def decoder(ids, vocab):
    inverse = {i: mot for mot, i in vocab.items()}   # Ex 9.5 en compréhension
    return " ".join(inverse[i] for i in ids)

assert decoder([1, 0], {"a": 0, "b": 1, "<unk>": 2}) == "b a"
```
`" ".join(liste)` colle les mots avec un espace : c'est l'inverse de `split()`.
</details>

**Ex 21.5** — 🏁 Assemble tout dans une classe `SimpleTokenizer(texte_entrainement)` avec `encode(texte)`, `decode(ids)` et `__len__` (taille du vocabulaire).
Test : entraîné sur `"le chat dort. le chien dort."`, `len(tok) == 6` et `tok.decode(tok.encode("le chat dort.")) == "le chat dort ."`, et `tok.encode("le loup")[1] == tok.vocab["<unk>"]`.
<details><summary>Correction</summary>

```python
class SimpleTokenizer:
    def __init__(self, texte_entrainement):
        tokens = self._tokeniser(texte_entrainement)
        self.vocab = {mot: i for i, mot in enumerate(sorted(set(tokens)))}
        self.vocab["<unk>"] = len(self.vocab)
        self.inverse = {i: mot for mot, i in self.vocab.items()}

    def _tokeniser(self, texte):
        texte = texte.lower().replace(",", " , ").replace(".", " . ")
        return texte.split()

    def encode(self, texte):
        return [self.vocab.get(t, self.vocab["<unk>"]) for t in self._tokeniser(texte)]

    def decode(self, ids):
        return " ".join(self.inverse[i] for i in ids)

    def __len__(self):
        return len(self.vocab)

tok = SimpleTokenizer("le chat dort. le chien dort.")
assert len(tok) == 6            # '.', 'chat', 'chien', 'dort', 'le', '<unk>'
assert tok.decode(tok.encode("le chat dort.")) == "le chat dort ."
assert tok.encode("le loup")[1] == tok.vocab["<unk>"]
```
🎉 C'est, à quelques détails près, le `SimpleTokenizerV2` du chapitre 2 de *Build a Large Language Model (from scratch)*. Tu es prêt à ouvrir le livre.
</details>

---

# 🧭 Après le 24 décembre

1. **Semaine de révision** (5 matins) : refais **uniquement l'exemple guidé** de 4 notions par jour, de mémoire.
2. **Janvier** : chapitre 1 du livre (lecture, 15 min/matin), puis chapitre 2 en retapant le code — tu reconnaîtras les notions 9, 11, 16 et 21.
3. Garde le même créneau : **5h35, 15 min**. La régularité est déjà construite, ne la casse pas.
