# analyse_action-yfinance
https://youtu.be/myFD0np9eys?si=Syis7g6k05qBsVPT


## Idées clés de la vidéo

La vidéo est un tutoriel d’initiation à Python appliqué à l’analyse de données boursières. Elle relie des notions fondamentales de programmation à la construction progressive d’un petit programme capable de récupérer des cours historiques et de comparer le prix de clôture à une moyenne mobile.

### 1. Apprendre les bases de Python par petits exemples

La vidéo commence par des exemples très simples afin d’introduire la syntaxe Python : afficher un message avec `print()`, répéter une instruction avec une boucle `while`, parcourir une liste avec une boucle `for` et générer une suite de valeurs avec `range()`.

L’objectif est de comprendre les trois éléments fondamentaux suivants :

| Notion | Rôle dans la vidéo | Exemple |
|---|---|---|
| `print()` | Afficher une information | `print("Hello World")` |
| Boucle `while` | Répéter une action tant qu’une condition est vraie | `while True:` |
| Boucle `for` | Parcourir une liste ou une séquence | `for x in range(10):` |
| Condition | Choisir une action selon une situation | `if`, `elif`, `else` |

### 2. Comprendre les conditions `if`, `elif` et `else`

La vidéo explique ensuite la logique conditionnelle. Un programme peut exécuter une instruction différente selon qu’une condition est vraie ou fausse. Cette structure devient essentielle dans le programme boursier, car elle permet de déterminer si le cours est au-dessus ou au-dessous d’une moyenne mobile.

Le principe général est le suivant :

> Si une condition est vraie, le programme exécute une première action ; sinon, il teste d’autres conditions ou exécute une action alternative.

### 3. Utiliser des bibliothèques spécialisées

Le tutoriel montre comment importer plusieurs bibliothèques Python : `pandas` pour manipuler les tableaux de données, `numpy` pour le calcul numérique, `datetime` pour gérer les dates et `yfinance`/`pandas_datareader` pour récupérer des données financières historiques.

L’idée importante est qu’un programme Python peut être construit à partir de bibliothèques existantes au lieu de développer soi-même tous les outils de téléchargement et de calcul.

### 4. Récupérer des données historiques d’une action

L’utilisateur saisit le symbole d’une action, par exemple `AAPL` ou `MSFT`. Le programme définit ensuite une date de début et utilise la date actuelle comme date de fin. Les données récupérées sont placées dans un **DataFrame pandas**, qui contient notamment les prix d’ouverture, de clôture, les plus hauts, les plus bas et les volumes.

Le DataFrame permet ensuite d’examiner les dernières lignes avec `tail()` et de réaliser des calculs sur les séries historiques.

### 5. Calculer une moyenne mobile simple de 50 jours

Le concept central du script final est la **moyenne mobile simple**, appelée SMA. Une SMA de 50 jours correspond à la moyenne des cours sur une fenêtre glissante de 50 séances.

Le programme compare ensuite chaque cours de clôture à cette moyenne :

| Situation | Interprétation utilisée dans le programme |
|---|---|
| Le cours de clôture est supérieur à la SMA | Le cours est considéré comme « higher » |
| Le cours de clôture est inférieur ou égal à la SMA | Le cours est considéré comme « lower » |

Le programme compte le nombre de jours appartenant à chaque catégorie à l’aide de deux variables, par exemple `numH` et `numC`.

### 6. Découvrir une logique de stratégie basée sur plusieurs EMA

Une autre partie présente une logique de type **RWB**, fondée sur plusieurs moyennes mobiles exponentielles. Les EMA courtes, telles que les EMA 3, 5, 8, 10, 12 et 15, sont comparées aux EMA plus longues, telles que les EMA 30, 35, 40, 45, 50 et 60.

Le signal d’achat étudié apparaît lorsque le minimum des EMA courtes est supérieur au maximum des EMA longues. En termes simples, cela signifie que l’ensemble des moyennes courtes se trouve au-dessus de l’ensemble des moyennes longues. Le programme vérifie ensuite si aucune position n’est déjà ouverte avant d’enregistrer un achat.

### 7. Comprendre le principe du backtesting

La vidéo introduit également le **backtesting**, c’est-à-dire l’application d’une règle de décision à des données historiques pour observer ce qui aurait pu se produire dans le passé.

La logique présentée suit approximativement ce cycle :

1. Parcourir les dates historiques une par une.
2. Calculer ou consulter les différentes moyennes mobiles.
3. Détecter une condition de signal.
4. Ouvrir une position si aucune position n’est déjà détenue.
5. Détecter ultérieurement une condition de sortie.
6. Comparer les prix d’achat et de vente pour estimer la performance.

La vidéo ne fournit toutefois pas une stratégie complète prête à être utilisée : certaines parties de la logique de vente et du calcul de performance ne sont pas entièrement visibles dans la transcription disponible.

### 8. Progression pédagogique du tutoriel

La vidéo suit une progression très graduelle : elle commence par `print()`, les boucles et les conditions, puis introduit les bibliothèques, les DataFrames, les dates, les moyennes mobiles et enfin une logique de backtesting. L’idée principale est de construire un programme plus complexe en assemblant des concepts simples.

## Résumé en une phrase

La vidéo montre comment passer des bases de Python à un programme d’analyse boursière qui télécharge des données historiques, calcule une moyenne mobile de 50 jours, compare le cours à cette moyenne et introduit une stratégie basée sur plusieurs moyennes mobiles exponentielles.

## Points à retenir avec prudence

Le programme présenté est avant tout un outil pédagogique. Le fait qu’un cours soit au-dessus d’une moyenne mobile ne constitue pas, à lui seul, une preuve qu’il faut acheter ou vendre une action. Un véritable backtest devrait également prendre en compte les frais, les écarts d’exécution, les dividendes, les divisions d’actions, la gestion du risque et le risque de surajustement.

### Référence

[1]: https://youtu.be/myFD0np9eys?si=Syis7g6k05qBsVPT — Vidéo YouTube fournie par l’utilisateur.
